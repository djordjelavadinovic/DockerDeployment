## Autmatic Build - Specification

1. Local copies of base images
2. Synchronization with source control system
3. Scheduling
4. Self-service for build
5. Log file keeping
6. Working with templates
7. Informing (developers, end-users)
8. Deploying on a test environment
9. Publishing
10. Static code analysis (Sonar Qube)
11. Unit testing
12. UI Testing
13. Integration testing
14. Provisioning of developer's boxes
15. Handling branches(?)

## Example of CI

https://blog.codecentric.de/en/2015/10/continuous-integration-platform-using-docker-container-jenkins-sonarqube-nexus-gitlab/

## Caching

NPM cache
Using Nexus https://www.theodo.fr/blog/2016/01/speed-up-npm-install-with-a-nexus-proxy-to-cache-packages/
(Nexus could be also used for Java librarires, not only for NodeJS)

Using npm-proxy-cache http://willcodefor.beer/setup-your-own-npm-cache-server/
