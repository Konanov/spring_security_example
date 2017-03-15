# todotoday
This application is used in the Treehouse workshop User Authentication in Spring. It is meant to demonstrate the use of Spring Security to implement user authentication and authorization.

Common Web App Attacks

# Brute Force Attack
Code Injection
Cross-Site Request Forgery (CSRF)
Cross-site Scripting (XSS)
Session fixation
SQL Injection


# Injecting User Data for Modifying Queries

If you want to inject user-specific data using the authentication object for INSERT statements, in the same way that we did for SELECT statements, you'll need to use a native query. Here is an example of a Spring Data JPA interface method that you could use:

@Modifying
@Transactional
@Query(nativeQuery = true, value = "insert into task (user_id,description,complete) values (:#{principal.id},:#{#task.description},:#{#task.complete})")
void saveForCurrentUser(@Param("task") Task task);
