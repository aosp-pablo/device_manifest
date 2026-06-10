# AxionOS for POCO F5 (marble)

## Requirements

Before you begin, ensure your system meets the following requirements:

- [Repo](https://source.android.com/docs/setup/reference/repo)
- [Git](https://git-scm.com/)
- Git Large File Storage (Git LFS)

## Sync AxionOS Source

First, sync the AxionOS source:

- https://github.com/AxionAOSP/android

## Adding the Local Manifest

1. Create the local manifests directory:

    ```bash
    mkdir -p .repo/local_manifests
    ```

2. Clone the local manifest repository:

    ```bash
    git clone -b axion https://github.com/aosp-pablo/device_manifest.git .repo/local_manifests
    ```

3. Sync device-specific sources:

    ```bash
    repo sync --force-sync --current-branch --no-clone-bundle --no-tags -j$(nproc --all)
    ```
## Build Flags

```bash
# Maintainer Name
AXION_MAINTAINER := (Your_name)
```

## Setup Environment

1. Navigate to the root directory of AxionOS:

    ```bash
    cd path/to/source
    ```

2. Run the environment setup script:

    ```bash
    source build/envsetup.sh
    ```
## Generate Private Keys

Run once before building:

```bash
gk -s
```

## Build Configuration

1. Lunch the target:

    ```bash
    axion marble user gms
    ```

## Compilation

1. Start the compilation process:

    ```bash
    m bacon
    ```

## Device Information

- Device: POCO F5 / Redmi Note 12 Turbo
- Codename: marble
- Platform: Qualcomm Snapdragon 7+ Gen 2 (SM7475)
