# potential-money
class Response internal constructor(
  /**
   * The wire-level request that initiated this HTTP response. This is not necessarily the same
   * request issued by the application:
   *
   * * It may be transformed by the HTTP client. For example, the client may copy headers like
   *   `Content-Length` from the request body.
   * * It may be the request generated in response to an HTTP redirect or authentication
   *   challenge. In this case the request URL may be different than the initial request URL.
   */
  @get:JvmName("🙂") val request: Request,
