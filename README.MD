1. SecurityContextHolder
   >SecurityContextHolder 为当前线程创建了一个 ThreadLocal 用于存放当前的 SecurityContext，既是当前 Spring Security 的上下文，包含对象，参数等任何一切与 Spring Security 相关的内容；不过，SecurityContextHolder 不一定非要将 SecurityContext 放置在线程中，比如 Swing client 客户端，用户的 Security Context 并不需要放置在一个线程中在，这个时候，可以通过设置 _SecurityContextHolder.MODE_GLOBAL_ 将 SecurityContext 放置在全局的环境之下；
2. Authentication
   >org.springframework.security.core.Authentication 是 java.security.Principal 的继承接口，提供了 Spring Security 额外需要的用户认证相关的接口信息，比如 Credentials，Details information，is Authenticated 等等信息；
3. AuthenticationManager
   >AuthenticationManager 提供了认证方法的入口，上述代码中可以清晰的看到，我们自定义实现了一个 SampleAuthenticationManager，提供对当前的用户进行认证；
4. UsernamePasswordAuthenticationToken
   >可以看到，该 Token 是 Authentication 的一个实现类，表示当前用户的认证信息
GrantedAuthority


**AuthenticationManager 对用户当前的 Authentication 既用户身份信息通过 authenticate 接口方法进行验证，若通过验证则返回被授权的 Authentication 对象，同时赋予其 AUTHORITIES，若认证失败，则抛出 AuthenticationException 异常；**

