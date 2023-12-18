# get-image-tag

A Github Action to create an image tag to be used for publishing a docker image.

If the workflow is triggered by a versioned release, it will use the release tag. 
If the workflow is not triggered by a versioned release, it will use the short commit hash.

## Usage

```yaml
    steps:
      - name: Checkout
        uses: actions/checkout@v2

      - name: Get Image Tag
        id: get_image_tag
        uses: patrickjmcd/get-image-tag@main

      - name: Build Tagged Image
        if: steps.get_image_tag.outputs.is_tag == 'true'
        ...
```
