### Step 1. Build image

    docker build -f ./Dockerfile.data --tag='doc-test-data' .

### Step 2. Create container (no needs to run container)

    docker create --name='doc-test-data' doc-test-data /bin/true

### Step 3. Mount data volume from "data container"

    docker run -it --rm --volumes-from='doc-test-data' alpine:3.5 sh
    cat /src/README.md
