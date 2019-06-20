Spring Boot

> @Autowired, @Qualifier, @Primary, @Required
https://www.youtube.com/watch?v=2YC5pIXR7e4

#import @Autowired in other class.
`@Autowired
private UserService userService;`
by 
`@Resource
private UserService userService`

#Daemonizer
It's obsolete.

#Reactive
One or few threads for many requests.
In general, it blocks the thread and create new one when e.g: trying to make IO request.

#Actuator
Debugging.
Used for private pages like: mappings, beans