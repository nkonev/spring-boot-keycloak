# spring-boot-keycloak
Using spring boot and Keycloak authorization server
https://habr.com/en/amp/post/552346/

Article about OpenID Connect
https://habr.com/en/post/422765/

Keycloak login/password - see in docker-compose.yml

Open user's keyclock page
http://localhost:8484/auth/realms/my_realm/account

Open keyclock admin console
http://localhost:8484/

Open protected page
http://localhost:8080/api/user

Configuring Keycloak - adding user:
1. Login as admin
2. Manage -> Users -> Add user
3. User's -> Credentials -> Set password, disable temporal
4. User's -> Role Mappings -> add 'USER' role

# Login as user1 (get 3 tokens)
```bash
curl -i -H 'Content-Type: application/x-www-form-urlencoded' 'http://localhost:8484/auth/realms/my_realm/protocol/openid-connect/token' -d 'client_id=my_client&grant_type=password&scope=openid&username=user1&password=user1'
```
