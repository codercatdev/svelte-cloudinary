---
title: CldUploadWidget/Configuration
order: 2
---
<script>
    import Table from '$lib/components/Table.svelte'
    import Callout from '$lib/components/Callout.svelte'
</script>

# CldUploadWidget Configuration

## Configuration

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
    }
  ]}
  data={[
    {
      prop: 'children',
      type: 'function',
      example: '<code>{(options) => {}}</code>',
      more: '',
    },
    {
      prop: 'options',
      type: 'object',
      example: '<code>{encryption: {...}}</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#parameters">More Info</a>'
    },
    {
      prop: 'signatureEndpoint',
      type: 'string',
      example: '<code>{`/api/sign-cloudinary-params.js`}</code>',
      more: '<a className="whitespace-nowrap" href="/clduploadwidget/signed-uploads">More Info</a>'
    },
    {
      prop: 'uploadPreset',
      type: 'string',
      example: '<code>{`my-upload-preset`}</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_presets">More Info</a>'
    },
  ]}
/>

### `children`

A function that returns a React component that receives instance methods and options for the widget.

```svelte
'<script>
  import { CldUploadWidget } from 'svelte-cloudinary'
</script>

<CldUploadWidget uploadPreset="<Upload Preset>" let:open>
      <button class="button" on:click={open}>
        Upload
      </button>
</CldUploadWidget>
```

### `options`

Parameters used to customize and configure the Upload Widget instance. These options are passed in
directly to the Upload Widget, exposing all available parameters through the `options` object.

```js
options={{
  sources: ['local', 'url', 'unsplash'],
  multiple: true,
  maxFiles: 5
}}
```

[Learn more about Upload Widget parameters](https://cloudinary.com/documentation/upload_widget_reference#parameters) on the Cloudinary docs.

### `signatureEndpoint`

An API endpoint used to sign the parameters generated during upload.

```jsx copy showLineNumbers
signatureEndpoint="/api/sign-cloudinary-params"
```

[Learn more about generating signatures](https://cloudinary.com/documentation/upload_images#generating_authentication_signatures) on the Cloudinary docs.

### `uploadPreset`

```js
uploadPreset="my-upload-preset"
```

[Learn more about upload presets](https://cloudinary.com/documentation/upload_presets) on the Cloudinary docs.


## Events

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
      prop: 'onAbort',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#abort">More Info</a>'
    },
    {
      prop: 'onBatchCancelled',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#batch_cancelled">More Info</a>'
    },
    {
      prop: 'onClose',
      type: 'function',
      example: '<code>(widget) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#close_event">More Info</a>'
    },
    {
      prop: 'onDisplayChanged',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#display_changed">More Info</a>'
    },
    {
      prop: 'onError',
      type: 'function',
      example: '<code>(error, widget) => { }</code>',
      more: ''
    },
    {
      prop: 'onOpen',
      type: 'function',
      example: '<code>(widget) => { }</code>',
      more: '',
    },
    {
      prop: 'onPublicId',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#publicid">More Info</a>',
    },
    {
      prop: 'onQueuesEnd',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#queues_end">More Info</a>'
    },
    {
      prop: 'onQueuesStart',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#queues_start">More Info</a>'
    },
    {
      prop: 'onRetry',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#retry">More Info</a>'
    },
    {
      prop: 'onShowCompleted',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#show_completed">More Info</a>'
    },
    {
      prop: 'onSourceChanged',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#source_changed">More Info</a>'
    },
    {
      prop: 'onSuccess',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#success">More Info</a>'
    },
    {
      prop: 'onTags',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#tags">More Info</a>'
    },
    {
      prop: 'onUpload',
      type: 'function',
      example: '<code>(results, widget) => { }</code>',
    },
    {
      prop: 'onUploadAdded',
      type: 'function',
      example: '<code>(results, options) => { }</code>',
      more: '<a className="whitespace-nowrap" href="https://cloudinary.com/documentation/upload_widget_reference#upload_added">More Info</a>'
    },
  ]}
/>

To learn more about the event callbacks and when they trigger, see: https://cloudinary.com/documentation/upload_widget_reference#events

**Example**

```jsx copy showLineNumbers
<CldUploadWidget
  ...
  onSuccess={(results) => {
    console.log('Public ID', results.info.public_id);
  }}
/>
```

### Callback Parameters

Most of the callbacks provide a set of options that give access to the results, options, and widget instance.


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
      id: 'description',
      title: 'Description'
    },
  ]}
  data={[
    {
      prop: 'error',
      type: 'string',
      description: 'If an error occurs, an explanation of what failed.'
    },
    {
      prop: 'options',
      type: 'object',
      description: 'Instance methods and the widget instance.'
    },
    {
      prop: 'results',
      type: 'object',
      description: 'The event that drove the callback and the info pertaining to the event (such as a resource).'
    },
  ]}
/>

<Callout emoji={false}>
Future releases will work to create a more consistent interface between older methods and more recently added methods.
</Callout>

**Example**

```jsx copy showLineNumbers
<CldUploadWidget
  ...
  onSuccess={(results) => {
    console.log('Public ID', results.info.public_id);
  }}
/>
```

#### `options`

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
      id: 'description',
      title: 'Description'
    },
  ]}
  data={[
    {
      prop: 'widget',
      type: 'Widget Instance',
      description: 'The Cloudinary Upload Widget instance being rendered.'
    },
    {
      prop: '[Instance Methods]',
      type: 'Function',
      description: '<span>See <a href="#instance-methods">Instance Methods</a> below</span>'
    },
  ]}
/>


#### `results`

The event and results that were returned from the event.

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
      id: 'description',
      title: 'Description'
    },
  ]}
  data={[
    {
      prop: 'event',
      type: 'string',
      description: 'The event that triggered the callback.'
    },
    {
      prop: 'info',
      type: 'string | object',
      description: 'Information pertaining to the triggered event, such as the resulting uploaded resource.'
    },
  ]}
/>

A common use of results could be to retrieve an uploaded asset, which would be made available in the `info` property
from the resulting event. If the result is a resource, the shape will include some of the following details.

**Example**

```js copy showLineNumbers
{
  height: 400;
  public_id: 'mypublicid';
  secure_url: 'https://res.cloudinary.com/.../mypublicid';
  width: 400;
  ...
}
```

## Child Function Parameters

By passing in a function as the child of the Upload Widget, you're able to gain access to the widget, results, and instance methods to interface directly with the widget.

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
      id: 'description',
      title: 'Description'
    },
  ]}
  data={[
    {
      prop: 'cloudinary',
      type: 'Cloudinary',
      description: 'The Cloudinary instance which creates and manages the Widget instance.'
    },
    {
      prop: 'error',
      type: 'string',
      description: 'The error, if any, produced by an upload widget action.'
    },
    {
      prop: 'isLoading',
      type: 'boolean',
      description: 'Designates whether the upload widget is loading and initializing.'
    },
    {
      prop: 'results',
      type: 'object',
      description: 'The event that triggered the results and information related to that event, which can include upload results.'
    },
    {
      prop: 'widget',
      type: 'Widget',
      description: 'The widget instance attached to the current component.'
    },
    {
      prop: '[Instance Methods]',
      type: 'Function',
      description: '<span>See <a href="#instance-methods">Instance Methods</a> below</span>'
    },
  ]}
/>

**Example**

```jsx copy showLineNumbers
<CldUploadWidget>
  {({ cloudinary, widget, open }) => {
    // Return UI
  }}
</CldUploadWidget>
```

## Instance Methods

The Upload Widget exposes instance methods that gives the ability to have greater control and flexbility over
the upload experience.

They're exposed either through event handler callback or child function parameters.

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
      id: 'description',
      title: 'Description'
    },
  ]}
  data={[
    {
      prop: 'close',
      type: 'function',
      description: 'Closes and resets the widget to its initial state without removing it from memory.'
    },
    {
      prop: 'destroy',
      type: 'function',
      description: 'Hides a previously rendered widget while retaining its current state in memory.'
    },
    {
      prop: 'hide',
      type: 'function',
      description: 'Closes the widget and completely removes it from the DOM. Returns a promise that resolves upon cleanup completion.'
    },
    {
      prop: 'isDestroyed',
      type: 'function',
      description: 'Returns whether the destroy method was called on this instance.'
    },
    {
      prop: 'isMinimized',
      type: 'function',
      description: 'Returns whether the widget is currently minimized.'
    },
    {
      prop: 'isShowing',
      type: 'function',
      description: 'Returns whether the widget is currently visible.'
    },
    {
      prop: 'minimize',
      type: 'function',
      description: 'Minimizes the widget.'
    },
    {
      prop: 'open',
      type: 'function',
      description: 'Renders an existing widget currently in memory, but that is not currently displayed.'
    },
    {
      prop: 'show',
      type: 'function',
      description: 'Renders a previously hidden widget.'
    },
    {
      prop: 'update',
      type: 'function',
      description: 'Updates a widget currently in memory with new options.'
    },
  ]}
/>
