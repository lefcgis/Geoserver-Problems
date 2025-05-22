# Geoserver-Problems
Algunas anécdotas de problemas resueltos en GeoServer.


Tenía una resticción para levantar GeoServer.

1. Fui a esta ruta: C:\xampp\tomcat\bin
2. Edité el starup.bat (Archivo por lotes de Windows) y debajo de "setlocal"
3. Coloqué lo siguiente: set geoserver.xframe.shouldSetPolicy=false
4. Guadar.
5. Fui a la siguiente ruta: C:\xampp\tomcat\webapps\geoserver\WEB-INF
6. Edité el archivo "web" (la parte que tenía comentarios con la palabra clave "apache").

   <!-- Uncomment following filter to enable CORS in Tomcat. Do not forget the second config block further down. -->    
    <filter>
       <filter-name>cross-origin</filter-name>
       <filter-class>org.apache.catalina.filters.CorsFilter</filter-class>
       <init-param>
         <param-name>cors.allowed.origins</param-name>
         <param-value>*</param-value>
       </init-param>
       <init-param>
         <param-name>cors.allowed.methods</param-name>
         <param-value>GET,POST,PUT,DELETE,HEAD,OPTIONS</param-value>
       </init-param>
       <init-param>
         <param-name>cors.allowed.headers</param-name>
         <param-value>*</param-value>
       </init-param>
    </filter>
    
8. Guardar el archivo web y listo.

