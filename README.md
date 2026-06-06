## Requirements

Before you begin, ensure your system meets the following requirements:

- [Repo](https://source.android.com/docs/setup/reference/repo)
- [Git](https://git-scm.com/)
- Git Large File Storage (Git LFS)

## Adding the Local Manifest

1. Create the local manifests directory:

    ```bash
    mkdir -p .repo/local_manifests
    ```

2. Clone the local manifest repository:

    ```bash
    git clone -b 16 https://github.com/aosp-pablo/device_manifest.git .repo/local_manifests
    ```

3. Remove old Xiaomi hardware sources if present:

    ```bash
    rm -rf hardware/xiaomi
    ```

4. Sync device-specific sources:

    ```bash
    repo sync --force-sync --current-branch --no-clone-bundle --no-tags -j$(nproc --all)
    ```
## Signed Build Keys

For signed builds, follow the instructions provided in the [Private Keys Template](https://gist.github.com/A2L5E0X1/54cb1b3a49030a9ebf8608b4e68073f5).

## ROM-Specific Bring-up

After syncing the manifest, bring up the device tree according to your target ROM source before building.

Example (Infinity X):

- https://github.com/aosp-pablo/device_xiaomi_marble/commit/2e5c3e5a35c5568e68148741533c250a8482537b

Additional ROM-specific changes may be required depending on the ROM source.

## Building

Once the bring-up is complete, follow your ROM's standard build instructions.

## Device Information

- Device: POCO F5 / Redmi Note 12 Turbo
- Codename: marble
- Platform: Qualcomm Snapdragon 7+ Gen 2 (SM7475)
