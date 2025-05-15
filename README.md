# Jenkins
* Orchestrates entire software delivery pipeline from building and testing to deployment.  <br>





* $JENKINS_HOME
    - tree `/var/lib/jenkins`
    - Jenkins Home directory is a crucial part of Jenkins setup, it stores all jenkins data and configuration.
    - Including jenkin jobs, plugins, configurations, logs, artifacts, archives and other metadata related to the jenkins server.
    - Need to be regularly backedup




---
### Jobs
- Define specific tasks such as compiling code, running tests, or deploying to an environment

### Builds
- Each execution of a job, with Jenkins maintaining a history for troubleshooting

### Freestyle project
- Default project type, offerieng flexible job definition

### Pipleine
- Chain jobs together to automate tasks from development to deployment

### Stages
- Group related jobs into phases like "build", "test", and "deploy" for clarity

### Nodes
- Machines wehre Jenkins executes jobs, with a single controller or multiple agents

### Plugins
- Extend Jenkins functionality, integrating with various tools and technologies.

---
# Jenkins Architecture

### Jenkins Controller Node (Master node)
- Plugins, Jobs, Nodes, Credentials, Configurations

1) Basic Deployment - controller node can handle all jobs
2) Advanced Deployment - Separate controller - worker nodes are needed

### Nodes (slaves)
