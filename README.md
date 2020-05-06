create project

    mkdir memcached-kubebuilder && cd memcached-kubebuilder

init go project

    go mod init example.com/memcached-kubebuilder

init kubebuilder

    kubebuilder init --domain example.com Memcached

create api and controller

    kubebuilder create api --group memcached --version v1 --kind Memcached

add spec and status in `api/v1/memcached_types.go`

  // MemcachedSpec defines the desired state of Memcached
  type MemcachedSpec struct {
      // INSERT ADDITIONAL SPEC FIELDS - desired state of cluster
      // Important: Run "make" to regenerate code after modifying this file

      //Quantity of instances
      Size int32 `json:"size"`
  }

  // MemcachedStatus defines the observed state of Memcached
  type MemcachedStatus struct {
      // INSERT ADDITIONAL STATUS FIELD - define observed state of cluster
      // Important: Run "make" to regenerate code after modifying this file

      //Status of pods
      Nodes []string `json:"nodes"`
  }

run `make` to update deepcopy files




# refs
https://github.com/dev4devs-com/memcached-kubebuilder


