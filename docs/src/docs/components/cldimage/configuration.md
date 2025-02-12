---
title: CldImage/Configuration
order: 2
---
<script>
    import Table from '$lib/components/Table.svelte'
    import Callout from '$lib/components/Callout.svelte'
</script>

<svelte:head>
  <title>CldImage Configuration - SvelteKit Cloudinary</title>
  <meta name="og:title" content="CldImage Configuration - SvelteKit Cloudinary" />
  <meta name="og:url" content={`https://svelte-cloudinary.vercel.app/components/cldimage/configuration`} />
</svelte:head>



# CldImage Configuration

The CldImage component provides a wide range of options for being able to easily optimize and transform images.

> Note: Configuration for CldImage is the same as [getCldImageUrl](/getcldimageurl/configuration), which both use the same underlying API.

## Required Props

The basic props required to use CldImage include:

<Table
  columns={[
  {
    id: 'prop',
    title: 'Prop'
  },
  {
    id: 'type',
    title: 'Type'
  },
  {
    id: 'required',
    title: 'Required'
  },
  {
    id: 'example',
    title: 'Example'
  },
  {
    id: 'more',
    title: 'More'
  },
]}
  data={[
  {
    prop: 'alt',
    type: 'string',
    required: 'Yes',
    example: "Dog catching a frisbee",
    more: '<a href="https://unpic.pics/img/svelte/">More Info</a>'
  },
  {
    prop: 'height',
    type: 'number/string',
    required: 'Yes ',
    example: '<code>600</code>',
    more: '<a href="https://unpic.pics/img/svelte/">More Info</a>'
  },
  {
    prop: 'src',
    type: 'string',
    required: 'Yes',
    example: '<code>my-public-id</code>',
    more: '',
  },
  {
    prop: 'width',
    type: 'number/string',
    required: 'Yes',
    example: '<code>600</code>',
    more: '<a href="https://unpic.pics/img/svelte/">More Info</a>'
  },
]}
/>

## Unpic Image Props

CldImage extends the Unpic Image component using Cloudinary tech. This means all props
available on the Unpic Image component are available on CldImage. Learn more on the
[Unpic Docs](https://unpic.pics/img/svelte/).


## Basic Transformations

The CldImage component exposes many of Cloudinary's transformations in an easy-to-use way
right inside of Svelte.

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'default',
      title: 'Default'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more'
    }
  ]}
  data={[
    {
      prop: 'background',
      type: 'string',
      default: '-',
      example: '<span><code>blue</code>, <code>rgb:0000ff</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#b_background">More Info</a>'
    },
    {
      prop: 'crop',
      type: 'string',
      default: '<code>limit</code>',
      example: '<code>thumb</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#c_crop_resize">More Info</a>'
    },
    {
      prop: 'fillBackground (Beta)',
      type: 'boolean | object',
      default: '-',
      example: '<code>{`{{ gravity: "east" }}`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#b_gen_fill">More Info</a>'
    },
    {
      prop: 'gravity',
      type: 'string',
      default: '<code>auto</code>',
      example: '<code>faces</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#g_gravity">More Info</a>'
    },
    {
      prop: 'recolor',
      type: 'array | object',
      default: '-',
      example: '<code>{`["duck", "blue"]`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_gen_recolor">More Info</a>'
    },
    {
      prop: 'remove',
      type: 'string | array | object',
      default: '-',
      example: '<code>{`apple`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_gen_remove">More Info</a>'
    },
    {
      prop: 'removeBackground',
      type: 'boolean | string',
      default: '<code>false</code>',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_background_removal">More Info</a>'
    },
    {
      prop: 'replace',
      type: 'array | object',
      default: '-',
      example: '<code>{`["apple", "banana"]`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_gen_replace">More Info</a>'
    },
    {
      prop: 'restore',
      type: 'boolean',
      default: '-',
      example: '<code>{`true`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_gen_restore">More Info</a>'
    },
    {
      prop: 'zoom',
      type: 'string',
      default: '-',
      example: '<code>0.5</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#z_zoom">More Info</a>'
    },
    {
      prop: 'zoompan',
      type: 'boolean | string | object',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_zoompan">More Info</a>'
    },
  ]}
/>

### `background`

Applies a background to empty or transparent areas.

**Examples**

```jsx copy
background="blue"
```

[Learn more about the background transformation](https://cloudinary.com/documentation/transformation_reference#b_background) on the Cloudinary docs.

### `crop`

Changes the size of the delivered asset according to the requested width & height dimensions.

**Examples**

```jsx copy
crop="fill"
```

[Learn more about the crop transformation](https://cloudinary.com/documentation/transformation_reference#c_crop_resize) on the Cloudinary docs.

### `fillBackground`

<Callout emoji={false} type="info">
  Generative Fill is currently in beta.
</Callout>

Automatically fills the padded area using generative AI to extend the image seamlessly.

The `fillBackground` prop can either be a boolean, which will use a set of safe defaults to produce
a background, or an object, which can take the following options:

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    }
  ]}
  data={[
    {
      prop: 'crop',
      type: 'string',
      example: '<code>clpad</code>',
    },
    {
      prop: 'gravity',
      type: 'string',
      example: '<code>south</code>',
    },
    {
      prop: 'prompt',
      type: 'string',
      example: '<code>cupcakes</code>',
    },
  ]}
/>

**Examples**

Applying Generative Fill with defaults:

```jsx copy
fillBackground
```

Customizing options:

```jsx copy
fillBackground={{
  crop: 'clpad',
  gravity: 'south',
  prompt: 'cupcakes'
}}
```

[Learn more about the Generative Fill transformation](https://cloudinary.com/documentation/transformation_reference#b_gen_fill) on the Cloudinary docs.

### `gravity`

Determines which part of an asset to focus on, and thus which part of the asset to keep, when any part of the asset is cropped

**Examples**

```jsx copy
gravity="face"
```

[Learn more about gravity](https://cloudinary.com/documentation/transformation_reference#g_gravity) on the Cloudinary docs.

### `recolor`

<Callout emoji={false} type="info">
  Generative Recolor is currently in beta.
</Callout>

Uses generative AI to recolor parts of your image, maintaining the relative shading.

The `recolor` prop can either be an array with the objects to be replaced or an object
with the following options:

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    }
  ]}
  data={[
    {
      prop: 'multiple',
      type: 'boolean',
      example: '<code>true</code>',
    },
    {
      prop: 'prompt',
      type: 'string | array',
      example: '<span><code>duck</code> or <code>["duck", "horse"]</code></span>',
    },
    {
      prop: 'to',
      type: 'string',
      example: '<code>blue</code>',
    },
  ]}
/>

**Examples**

Recoloring an object with an array:

```jsx copy
recolor={["duck", "blue"]}
```

Or using the object format:

```jsx copy
recolor={{
  prompt: "duck",
  to: "blue",
  multiple; true
}}
```

[Learn more about the Generative Recolor transformation](https://cloudinary.com/documentation/transformation_reference#e_gen_recolor) on the Cloudinary docs.

### `remove`

<Callout emoji={false} type="info">
  Generative Remove is currently in beta.
</Callout>

Uses generative AI to remove unwanted parts of your image, replacing the area with realistic pixels.

The `remove` prop can either be a string, an array, or an object with the following options:

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    }
  ]}
  data={[
    {
      prop: 'multiple',
      type: 'boolean',
      example: '<code>true</code>',
    },
    {
      prop: 'prompt',
      type: 'string | array',
      example: '<span><code>duck</code> or <code>["duck", "horse"]</code></span>',
    },
    {
      prop: 'removeShadow',
      type: 'boolean',
      example: '<code>true</code>',
    },
    {
      prop: 'region',
      type: 'array',
      example: '<code>[300, 200, 1900, 3500]</code>',
    },
  ]}
/>

**Examples**

Removing an object by string:

```jsx copy
remove="apple"
```

Removing multiple objects by array:

```jsx copy
remove={["apple", "banana", 'orange']}
```

Removing multiple instances of an object and their shadow with object configuration:

```jsx copy
remove={{
  prompt: "apple",
  multiple: true,
  removeShadow: true
}}
```

Removing a region:

```jsx copy
remove={{
  region: [300, 200, 1900, 3500]
}}
```

Removing multiple regions:

```jsx copy
remove={{
  region: [
    [300, 200, 1900, 3500],
    [123, 321, 750, 500]
  ]
}}
```

[Learn more about the Generative Remove transformation](https://cloudinary.com/documentation/transformation_reference#e_gen_remove) on the Cloudinary docs.

### `removeBackground`

Uses the [Cloudinary AI Background Removal add-on](https://cloudinary.com/documentation/cloudinary_ai_background_removal_addon) to make the background of an image transparent.

<Callout emoji={false} type="info">
  The Cloudinary AI Background Removal add-on is required to use this feature.
</Callout>


**Examples**

```jsx copy
removeBackground
```

[Learn more about background removal transformation](https://cloudinary.com/documentation/transformation_reference#e_background_removal) on the Cloudinary docs.


### `replace`

<Callout emoji={false} type="info">
  Generative Replace is currently in beta.
</Callout>

Uses generative AI to replace parts of your image with something else.

The `replace` prop can either be an array with the objects to be replaced or an object
with the following options:

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    }
  ]}
  data={[
    {
      prop: 'from',
      type: 'string',
      example: '<code>apple</code>',
    },
    {
      prop: 'to',
      type: 'string',
      example: '<code>banana</code>',
    },
    {
      prop: 'preserveGeometry',
      type: 'boolean',
      example: '<code>true</code>',
    },
  ]}
/>

**Examples**

Replacing an object with an array:

```jsx copy
replace={["apple", "banana"]}
```

Or using the object format:

```jsx copy
replace={{
  from: "apple",
  to: "banana",
  preserveGeometry; true
}}
```

[Learn more about the Generative Replace transformation](https://cloudinary.com/documentation/transformation_reference#e_gen_replace) on the Cloudinary docs.

### `restore`

<Callout emoji={false} type="info">
  Generative Restore is currently in beta.
</Callout>

Uses generative AI to restore details in poor quality images or images that may have become degraded through repeated processing and compression.

The `restore` prop can be used as a boolean.

**Examples**

```jsx copy
restore
```

[Learn more about the Generative Restore transformation](https://cloudinary.com/documentation/transformation_reference#e_gen_restore) on the Cloudinary docs.


### `zoom`

Controls how close to crop to the detected coordinates when using face-detection, custom-coordinate, or object-specific gravity.

**Examples**

```jsx copy
zoom="0.75"
```

[Learn more about the zoom transformation](https://cloudinary.com/documentation/transformation_reference#z_zoom) on the Cloudinary docs.

### `zoompan`

Also known as the Ken Burns effect, this transformation applies zooming and/or panning to an image, resulting in a video or animated GIF.

`zoompan` can be applied with safe defaults as a boolean, a string, or an object for
advanced customization.

As a string, you can pass in "loop" to automatically loop, or you can pass in raw configuration using the Cloudinary
Transformation syntax.

As an object, you can use advanced configuration with the following options:

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    }
  ]}
  data={[
    {
      prop: 'loop',
      type: 'boolean | string',
      example: '<code>true</code>',
    },
    {
      prop: 'options',
      type: 'boolean | string',
      example: '<code>mode_ztr;maxzoom_6.5;du_10</code>',
    },
  ]}
/>

**Examples**

With defaults:

```jsx copy
zoompan
```

Add looping:

```jsx copy
zoompan="loop"
```

Customize options:

```jsx copy
zoompan={{
  loop: 'loop:2', // Will loop twice
  options: 'mode_ztr;maxzoom_6.5;du_10'
}}
```

[Learn more about the zoompan transformation](https://cloudinary.com/documentation/transformation_reference#e_zoompan) on the Cloudinary docs.


## Filters & Effects

Cloudinary supports a wide variety of effects and artistic filters that help
to easily change the appearance of an image.

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'default',
      title: 'Default'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more'
    }
  ]}
  data={[
    {
      prop: 'art',
      type: 'string',
      default: '-',
      example: '<code>al_dente</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_art">More Info</a>'
    },
    {
      prop: 'autoBrightness',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>80</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_auto_brightness">More Info</a>'
    },
    {
      prop: 'autoColor',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>80</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_auto_color">More Info</a>'
    },
    {
      prop: 'autoContrast',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>80</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_auto_contrast">More Info</a>'
    },
    {
      prop: 'assistColorblind',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>20</code>, <code>xray</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_assist_colorblind">More Info</a>'
    },
    {
      prop: 'blackwhite',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>40</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_blackwhite">More Info</a>'
    },
    {
      prop: 'blur',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>800</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_blur">More Info</a>'
    },
    {
      prop: 'blurFaces',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>800</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_blur_faces">More Info</a>'
    },
    {
      prop: 'blurRegion',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>1000,h_425,w_550,x_600,y_400</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_blur_region">More Info</a>'
    },
    {
      prop: 'border',
      type: 'string',
      default: '-',
      example: '<code>5px_solid_purple</code>',
      more: '',
    },
    {
      prop: 'brightness',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>100</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_brightness">More Info</a>'
    },
    {
      prop: 'brightnessHSB',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>100</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_brightness_hsb">More Info</a>'
    },
    {
      prop: 'cartoonify',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>70:80</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_cartoonify">More Info</a>'
    },
    {
      prop: 'color',
      type: 'string',
      default: '-',
      example: '<code>blue</code>',
      more: '',
    },
    {
      prop: 'colorize',
      type: 'string',
      default: '-',
      example: '<code>35,co_darkviolet</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_colorize">More Info</a>'
    },
    {
      prop: 'contrast',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>100</code>, <code>level_-70</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_contrast">More Info</a>'
    },
    {
      prop: 'distort',
      type: 'string',
      default: '-',
      example: '<span><code>150:340:1500:10:1500:1550:50:1000</code>, <code>arc:180.0</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_distort">More Info</a>'
    },
    {
      prop: 'fillLight',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>70:20</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_fill_light">More Info</a>'
    },
    {
      prop: 'gamma',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>100</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_gamma">More Info</a>'
    },
    {
      prop: 'gradientFade',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>symmetric:10,x_0.2,y_0.4</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_gradient_fade">More Info</a>'
    },
    {
      prop: 'grayscale',
      type: 'bool',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_grayscale">More Info</a>'
    },
    {
      prop: 'improve',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>50</code>, <code>indoor</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_improve">More Info</a>'
    },
    {
      prop: 'multiply',
      type: 'bool',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_multiply">More Info</a>'
    },
    {
      prop: 'negate',
      type: 'bool',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_negate">More Info</a>'
    },
    {
      prop: 'oilPaint',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>40</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_oil_paint">More Info</a>'
    },
    {
      prop: 'opacity',
      type: 'number/string',
      default: '-',
      example: '<code>40</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#o_opacity">More Info</a>'
    },
    {
      prop: 'outline',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>40</code>, <code>outer:15:200</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_outline">More Info</a>'
    },
    {
      prop: 'overlay',
      type: 'bool',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_overlay">More Info</a>'
    },
    {
      prop: 'pixelate',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>20</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_pixelate">More Info</a>'
    },
    {
      prop: 'pixelateFaces',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>20</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_pixelate_faces">More Info</a>'
    },
    {
      prop: 'pixelateRegion',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>35,h_425,w_550,x_600,y_400</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_pixelate_region">More Info</a>'
    },
    {
      prop: 'redeye',
      type: 'boolean | string',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_redeye">More Info</a>'
    },
    {
      prop: 'replaceColor',
      type: 'string',
      default: '-',
      example: '<span><code>saddlebrown</code>, <code>2F4F4F:20</code>, <code>silver:55:89b8ed</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_replace_color">More Info</a>'
    },
    {
      prop: 'sanitize',
      type: 'bool',
      default: '<span><code>true</code> if .svg</span>',
      example: '<span><code>true</code> - Only applies to .svg</span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#fl_sanitize">More Info</a>'
    },
    {
      prop: 'saturation',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>70</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_saturation">More Info</a>'
    },
    {
      prop: 'screen',
      type: 'bool',
      default: '-',
      example: '<code>true</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_screen">More Info</a>'
    },
    {
      prop: 'sepia',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>50</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_sepia">More Info</a>'
    },
    {
      prop: 'shadow',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>50,x_-15,y_15</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_shadow">More Info</a>'
    },
    {
      prop: 'sharpen',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>100</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_sharpen">More Info</a>'
    },
    {
      prop: 'shear',
      type: 'string',
      default: '-',
      example: '<code>20.0:0.0</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_shear">More Info</a>'
    },
    {
      prop: 'simulateColorblind',
      type: 'boolean | string',
      default: '-',
      example: '<code>deuteranopia</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_simulate_colorblind">More Info</a>'
    },
    {
      prop: 'tint',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>100:red:blue:yellow</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_tint">More Info</a>'
    },
    {
      prop: 'trim',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>50:yellow</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_trim">More Info</a>'
    },
    {
      prop: 'unsharpMask',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>500</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_unsharp_mask">More Info</a>'
    },
    {
      prop: 'vectorize',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>3:0.5</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_vectorize">More Info</a>'
    },
    {
      prop: 'vibrance',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>70</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_vibrance">More Info</a>'
    },
    {
      prop: 'vignette',
      type: 'boolean | string',
      default: '-',
      example: '<span><code>true</code>, <code>30</code></span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#e_vignette">More Info</a>'
    }
  ]}
/>

**Examples**

Make an image black and white:

```jsx copy
blackwhite
```

Pixelate an image:

```jsx copy
pixelate
```

Sharpen an image:

```jsx copy
sharpen={50}
```

[View the Cloudinary docs](https://cloudinary.com/documentation/transformation_reference#e_effect) to see learn more about using effects.

## Overlays & Underlays

Cloudinary gives you the ability to add layers above or below your primary asset using Overlays and Underlays.

<Table
  columns={[
{
  id: 'prop',
  title: 'Prop'
},
{
  id: 'type',
  title: 'Type'
},
{
  id: 'example',
  title: 'Example'
},
]}
  data={[
  {
    prop: 'overlays',
    type: 'array',
    default: '-',
    example: '<a href="#customizing-overlays--underlays">Customizing Overlays & Underlays</a>',
  },
  {
    prop: 'text',
    type: 'string',
    default: '-',
    example: '<code>Svelte Cloudinary</code>',
  },
  {
    prop: 'underlay',
    type: 'string',
    default: '-',
    example: '<code>my-public-id</code>',
  },
  {
    prop: 'underlays',
    type: 'array',
    default: '-',
    example: '<a href="#customizing-overlays--underlays">Customizing Overlays & Underlays</a>',
  },
]}
/>

### Customizing Overlays & Underlays

> Note: The API for Underlays is similar to Overlays except they do not support text.

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    },
  ]}
  data={[
    {
      prop: 'appliedEffects',
      type: 'array',
      example: '<span><a href="#layer-effect-props">effects</a>, added as applied transformation</span>',
    },
    {
      prop: 'effects',
      type: 'array',
      example: '<a href="#layer-effect-props">effects</a>',
    },
    {
      prop: 'position',
      type: 'object',
      example: '<a href="#layer-position-props">position</a>',
    },
    {
      prop: 'publicId',
      type: 'string',
      example: '<code>mypublicid</code>',
    },
    {
      prop: 'text',
      type: 'object|string',
      example: '<span><code>Svelte Cloudinary</code> or See <a href="#layer-text-props">text</a> Below</span>',
    },
    {
      prop: 'url',
      type: 'string',
      example: '<code>https://.../image.jpg</code>',
    },
  ]}
/>

**Examples**

Adding an overlay:

```jsx copy
overlays={[{
  publicId: 'images/earth',
  position: {
    x: 50,
    y: 50,
    gravity: 'north_west',
  },
  appliedEffects: [
    {
      multiply: true
    }
  ]
}]}
```

Adding an underlay:

```jsx copy
underlays={[{
  publicId: 'images/earth',
}]}
```

<div class="-mb-4">
  <strong id="layer-effect-props" class="block text-slate-500 text-lg mt-8 -mb-4">
    <code>effects</code>
  </strong>

  Objects in the `effects` array can include everything in [Basic Transformations](#basic-transformations) and [Filters & Effects](#filters--effects) above as well as:
</div>

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more',
    },
  ]}
  data={[
    {
      prop: 'aspectRatio',
      type: 'string',
      example: '<code>3.0</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#ar_aspect_ratio">More Info</a>'
    },
    {
      prop: 'crop',
      type: 'string',
      example: '<code>10</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#c_crop_resize">More Info</a>'
    },
    {
      prop: 'gravity',
      type: 'string',
      example: '<code>north_west</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#g_gravity">More Info</a>'
    },
    {
      prop: 'height',
      type: 'number',
      example: '<code>600</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#h_height">More Info</a>'
    },
    {
      prop: 'width',
      type: 'number',
      example: '<code>600</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#w_width">More Info</a>'
    },
  ]}
/>

<div class="-mb-4">
  <strong id="layer-position-props" class="block text-slate-500 text-lg mt-8 -mb-4">
    <code>position</code>
  </strong>

  The `position` property can include:
</div>

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more'
    },
  ]}
  data={[
    {
      prop: 'angle',
      type: 'number',
      example: '<code>45</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#a_angle">More Info</a>'
    },
    {
      prop: 'gravity',
      type: 'string',
      example: '<code>north_west</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#g_gravity">More Info</a>'
    },
    {
      prop: 'x',
      type: 'number',
      example: '<code>10</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#x_y_coordinates">More Info</a>'
    },
    {
      prop: 'y',
      type: 'number',
      example: '<code>10</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#x_y_coordinates">More Info</a>'
    },
  ]}
/>

<div class="-mb-4">
  <strong id="layer-text-props" class="block text-slate-500 text-lg mt-8 -mb-4">text</strong>

  The `text` property can include:
</div>

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more',
    },
  ]}
  data={[
    {
      prop: 'border',
      type: 'string',
      example: '<code>20px_solid_blue</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#bo_border">More Info</a>'
    },
    {
      prop: 'color',
      type: 'string',
      example: '<code>blueviolet</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#co_color">More Info</a>'
    },
    {
      prop: 'fontFamily',
      type: 'string',
      example: '<code>Open Sans</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
    {
      prop: 'fontSize',
      type: 'number',
      example: '<code>48</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
    {
      prop: 'fontWeight',
      type: 'string',
      example: '<code>bold</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
    {
      prop: 'letterSpacing',
      type: 'number',
      example: '<code>14</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
    {
      prop: 'lineSpacing',
      type: 'number',
      example: '<code>14</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
    {
      prop: 'stroke',
      type: 'bool',
      example: '<span><code>true</code> in coordination with Border</span>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
    {
      prop: 'textDecoration',
      type: 'string',
      example: '<code>underline</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#styling_parameters">More Info</a>'
    },
  ]}
/>

## Advanced

### Configuration & Delivery

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'default',
      title: 'Default'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more'
    }
  ]}
  data={[
    {
      prop: 'config',
      type: 'object',
      default: '-',
      example: '<code>{`{ url: { secureDistribution: "svelte.cloudinary.dev" } }`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/cloudinary_sdks#configuration_parameters">More Info</a>'
    },
    {
      prop: 'deliveryType',
      type: 'string',
      default: '<code>upload</code>',
      example: '<code>fetch</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/image_transformations#delivery_types">More Info</a>'
    },
    {
      prop: 'defaultImage',
      type: 'string',
      default: '-',
      example: '<code>myimage.jpg</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#d_default_image">More Info</a>'
    },
    {
      prop: 'flags',
      type: 'array',
      default: '-',
      example: '<code>{`["keep_iptc"]`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/transformation_reference#fl_flag">More Info</a>'
    },
    {
      prop: 'seoSuffix',
      type: 'string',
      default: '-',
      example: '<code>my-image-content</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/advanced_url_delivery_options#dynamic_seo_suffixes">More Info</a>'
    },
    {
      prop: 'version',
      type: 'number',
      default: '-',
      example: '<code>1234</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/advanced_url_delivery_options#asset_versions">More Info</a>'
    },
  ]}
/>

#### `config`

Allows configuration for the Cloudinary environment.

**Examples**

```jsx copy
config={{
  cloud: {
    cloudName: 'my-cloud'
  }
}}
```

[Learn more about configuration parameters](https://cloudinary.com/documentation/cloudinary_sdks#configuration_parameters) on the Cloudinary docs.

#### `deliveryType`

Controls the delivery type of the image.

**Examples**

```jsx copy
deliveryType="fetch"
```

[Learn more about Delivery Types](https://cloudinary.com/documentation/image_transformations#delivery_types) on the Cloudinary docs.

#### `defaultImage`

Configures the default image to use in case the given public ID is not available.

<Callout emoji={false} type="info">
  `defaultImage` must include a format / file extension.
</Callout>

**Examples**

```jsx copy
defaultImage="myimage.jpg"
```

[Learn more about Default Images](https://cloudinary.com/documentation/transformation_reference#d_default_image) on the Cloudinary docs.

#### `flags`

Alters the regular behavior of another transformation or the overall delivery behavior.

<Callout emoji={false}>
  The `keep_iptc` flag requires not including a quality of auto. Using `quality="default"` avoids setting the quality flag in the URL.
</Callout>

**Examples**

```jsx copy
flags={['keep_iptc']}
quality="default"
```

[Learn more about Flags](https://cloudinary.com/documentation/transformation_reference#fl_flag) on the Cloudinary docs.

#### `seoSuffix`

Adds a dynamic, descriptive suffix to the Public ID for greater SEO control of image URLs.

**Examples**

```jsx copy
seoSuffix="jellyfish-in-space"
```

[Learn more about Dynamic SEO Suffixes](https://cloudinary.com/documentation/advanced_url_delivery_options#dynamic_seo_suffixes) on the Cloudinary docs.

#### `version`

Controls the version defined in the delivery URL.

**Examples**

```jsx copy
version="1234"
```

[Learn more about Asset Versions](https://cloudinary.com/documentation/advanced_url_delivery_options#asset_versions) on the Cloudinary docs.


### Events & Refs

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more',
    },
  ]}
  data={[
    {
      prop: 'onError',
      type: 'function/bool',
      example: '<code>{`(event) => {}`}</code>',
      more: ''
    },
    {
      prop: 'ref',
      type: 'ref',
      example: 'Ref',
      more: '<a class="whitespace-nowrap" href="https://react.dev/reference/react/useRef">More Info</a>'
    },
  ]}
/>

#### `onError`

Callback that fire when an image fails to load.

Upon failure, if the resulting HTTP status is a 423 (Processing), CldImage will attempt to poll the URL
until it's available, then force refresh the image instance in the DOM.

**Examples**

```jsx copy
onError={() => {
  alert('Image failed to load!')
}}
```


### Managing Transformations

Most transformations and effects are exposed as top-level props to enable you to easily
apply what you need, but you can also use the following props for more advanced and
organized ways of applying transformations and effects.

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'default',
      title: 'Default'
    },
    {
      id: 'example',
      title: 'Example'
    },
    {
      id: 'more'
    }
  ]}
  data={[
    {
      prop: 'effects',
      type: 'array',
      default: '-',
      example: '<code>{`[{ background: "blue" }]`}</code>'
    },
    {
      prop: 'preserveTransformations',
      type: 'string',
      default: '<code>false</code>',
      example: '<code>true</code>',
      more: '',
    },
    {
      prop: 'rawTransformations',
      type: 'array',
      default: '-',
      example: '<code>{`["e_blur:2000"]`}</code>',
      more: '',
    },
    {
      prop: 'strictTransformations',
      type: 'boolean',
      default: '-',
      example: '<a href="#stricttransformations">Strict Transformations</a>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/control_access_to_media#strict_transformations">More Info</a>'
    },
    {
      prop: 'transformations',
      type: 'string | array',
      default: '-',
      example: '<code>{`["my-named-transformation"]`}</code>',
      more: '<a class="whitespace-nowrap" href="https://cloudinary.com/documentation/image_transformations#named_transformations">More Info</a>'
    },
  ]}
/>

#### `effects`

Applies a chain of transformation sets to an image.

**Examples**

```jsx copy
effects={[
  {
    width: 100,
    height: 100,
    crop: 'fill'
  },
  {
    opacity: 50
  }
]}
```

#### `preserveTransformations`

Preserves transformations already applied to an image when passing in a Cloudinary URL
as the `src`.

**Examples**

```jsx copy
preserveTransformations
```

#### `rawTransformations`

Provides the ability to pass in an array of "raw" Cloudinary transformations using the
[Transformation URL API](https://cloudinary.com/documentation/transformation_reference)

**Examples**

```jsx copy
rawTransformations={['w_100', 'b_blue', 'f_auto']}
```

#### `strictTransformations`

[Strict Transformations](https://cloudinary.com/documentation/control_access_to_media#strict_transformations) gives
you the ability to have more control over what transformations are permitted to be used from your Cloudinary account.

By enabling Strict Transformations, you restrict the ability to generate transformations on-the-fly requiring explicit
approval through the Cloudinary dashboard.

> Note: This disables [optimization](#optimization) and [responsive sizing](/guides/responsive-images)
only allowing [named transformations](#transformations) to be applied. The width and height are not applied to the URL,
but are still included on the image tag rendered to the DOM.

**Examples**

```jsx copy
strictTransformations
transformations=["my-transformation"]
```

[Learn more about Strict Transformations](https://cloudinary.com/documentation/control_access_to_media#strict_transformations) on the Cloudinary docs.

#### `transformations`

Applies named transformations to the image.

**Examples**

```jsx copy
transformations={['my-transformation']}
```

[Learn more about Named Transformations](https://cloudinary.com/documentation/image_transformations#named_transformations) on the Cloudinary docs.


### Optimization

By default, CldImage opts in any image to `f_auto` and `q_auto` which provide automatic
optimization through intelligent compression and by automatically delivering the most
efficient format based on the browser and device requesting the image.

You can customize and manage these properties using the options below:

<Table
  columns={[
    {
      id: 'prop',
      title: 'Prop'
    },
    {
      id: 'type',
      title: 'Type'
    },
    {
      id: 'default',
      title: 'Default'
    },
    {
      id: 'example',
      title: 'Example'
    },
  ]}
  data={[
    {
      prop: 'dpr',
      type: 'number/string',
      default: '-',
      example: '<code>2.0</code>',
    },
    {
      prop: 'format',
      type: 'string',
      default: '<code>auto</code>',
      example: '<code>webp</code>',
    },
    {
      prop: 'quality',
      type: 'string',
      default: '<code>auto</code>',
      example: '<code>90</code>',
    },
    {
      prop: 'unoptimized',
      type: 'boolean',
      default: '-',
      example: '',
    },
  ]}
/>

#### `dpr`

Sets the device pixel ratio (DPR) for the delivered image or video using a specified value or automatically based on the requesting device.

**Examples**

```jsx copy
dpr="2.0"
```

[Learn more about configuring DPR](https://cloudinary.com/documentation/transformation_reference#dpr_dpr) on the Cloudinary docs.


#### `format`

Converts (if necessary) and delivers an asset in the specified format regardless of the file extension used in the delivery URL.

**Examples**

```jsx copy
format="png"
```

[Learn more about format](https://cloudinary.com/documentation/transformation_reference#f_format) on the Cloudinary docs.


#### `quality`

Controls the quality of the delivered asset. Reducing the quality is a trade-off between visual quality and file size.

**Examples**

```jsx copy
quality="10"
```

[Learn more about quality](https://cloudinary.com/documentation/transformation_reference#q_quality) on the Cloudinary docs.


