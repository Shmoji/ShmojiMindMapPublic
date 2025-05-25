  * Kubernetes
    * Terms
      * Volumes
        * My reasoning for volumes: containers meant to get deleted, volumes allow data to be persisted
        * Kubernetes volumes are a mechanism for persisting data in a containerized application deployed on a Kubernetes cluster. The reason for using volumes is to allow data to persist even if the container itself is deleted, recreated, or moved to a different host. This is important because containers are meant to be ephemeral, meaning that their contents can disappear at any time.
        * In simple terms, a Kubernetes volume is a way to store data outside of a container, so that it can persist even if the container is deleted, recreated or moved.
        * At its core, a volume is a directory, possibly with some data in it, which is accessible to multiple containers in a pod. How that directory comes to be, the medium that backs it, and the contents of it are determined by the particular volume type used.

  * related
    * [[docker]]
