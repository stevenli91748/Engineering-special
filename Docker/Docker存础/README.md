


* [Bind Mount--filesystem](#Bind)
* [Volume--filesystem](#Volume)
* [Tmpfs mount---memory](#Tmpfs)
* [named pipes](#named-pipes)

# Bind

   may be stored anywhere on the host system. They may even be important system files or directories. Non-Docker processes on the Docker 
   host or a Docker container can modify them at any time
   
   The docker provides DNS resolution to container by mounting /etc/resolv.conf from the host machine into each container

# Volume

   Volumes are stored in a part of the host filesystem which is managed by Docker (/var/lib/docker/volumes/<volume-name> on Linux)

# Tmpfs

   mounts are stored in the host system’s memory only, and are never written to the host system’s filesystem.
   
# named pipes
