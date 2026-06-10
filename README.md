# Project Infinity X for POCO F5 (marble)

## Requirements

Before you begin, ensure your system meets the following requirements:

- [Repo](https://source.android.com/docs/setup/reference/repo)
- [Git](https://git-scm.com/)
- Git Large File Storage (Git LFS)

## Sync Infinity X Source

First, sync the Infinity X source:

- https://github.com/ProjectInfinity-X/manifest

## Adding the Local Manifest

1. Create the local manifests directory:

    ```bash
    mkdir -p .repo/local_manifests
    ```

2. Clone the local manifest repository:

    ```bash
    git clone -b infinity https://github.com/aosp-pablo/device_manifest.git .repo/local_manifests
    ```

3. Sync device-specific sources:

    ```bash
    repo sync --force-sync --current-branch --no-clone-bundle --no-tags -j$(nproc --all)
    ```

## Build Flags

```bash
# Maintainer Name
INFINITY_MAINTAINER := "YourInput" (Default: Unknown)

# Whether Including Google Apps
WITH_GAPPS := true/false (Default: true)
```

## Setup Environment

1. Navigate to the root directory of Project Infinity X:

    ```bash
    cd path/to/source
    ```

2. Run the environment setup script:

    ```bash
    source build/envsetup.sh
    ```
## Signed Build Keys

For signed builds, follow the instructions provided in the [Infinity Private Keys Template](https://github.com/ProjectInfinity-X/vendor_infinity-priv_keys-template) repository.

## Build Configuration

1. Lunch the target:

    ```bash
    lunch infinity_marble-user
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
