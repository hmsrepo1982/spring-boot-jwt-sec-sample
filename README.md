# spring-boot-jwt-sec-sample

JWT - Jason Web Token

Authorization Stratergies 

- Session Token
- JWT

1. Http being Stateless wont remember what is previous request is. What are the implications.
2. Rendering any page from web server - send URL and who am i. Each request needs this information.
3. If this source of truth, then how some times Applications remembers you. Eg : Banking Application Knows who you are till you log off or till your session is timedout.
4. How does this is done.
      - Session Token : 
      Once Authenticated user data is maintained in some kind of Session Logs.
      from then onwards, always same session Token is passed in every other request - Whom am I.
      Session Id mostly sent in Cookie Header
      This is working till today from Authorization perspective.
      Assumption made is - One server, data access is easy at it is at once place.
      
      Eg : Imagine load Balancer case - Server 1, Server 2 and Server 3. Introduces shared Session Log Data.
      
      What is the issue - Shared Session data is one point of failure.
      
      Comes in - Sticky Session where, its always tied to same server which is in Cluster. Server needs to managed this.
      
 5. To change this JWT was introduced where Interaction contract would be changed.
    
    - Anyone calls now a service would get complete contract as a Hashed content back to client.
    - From then onwards - they each time this Hashed content will be passed back in
   
   
   https://jwt.io/ - look at - Algorithm that is used # HS256.
   
   Encoded section -  --->  Header | PAYLOAD | SIGNATURE 
   
   Understand this section and then look at the code that is built for this. 
   
   6. Some short comings in JWT 


