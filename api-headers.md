# API Headers

After [Signing Up](signing-up.md) and [Logging In](loggin-in.md), all queries and mutations must have the following headers.

```JavaScript
{
    "Content-Type": "application/json",
    "Authorization": "{AUTH_TOKEN}"
}
```

These headers must be past in for each query and mutation call to the server.

Best place to support this is in the client HTTP Interceptor so it uses authorization for every API call.

> **Angular 5+**

```
@Injectable()
export class HttpInterceptorRequestService implements HttpInterceptor {

  public intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {

    req = req.clone({
      setHeaders: GlobalsConstants.TOKEN ? this.getHeaders() : {},
      reportProgress: true,
      withCredentials: false
    });
    return next.handle(req);
  }

  private getHeaders() {
    return {
      Content-Type: 'application/json',
      Authorization: '{AUTH_TOKEN}'
    };
  }

}
```