# svelte-meta-data

*svelte-meta-data* is a svelte component used to manage all relevant meta data related to your website. This component was made to emulate the blog_info method from WordPress so you can access site meta data throughout your app with ease. This component also automates the creation of meta tags for SEO purposes. Simply pass an object containing all site &amp; SEO meta data to the component via props and voila!

> ⚠️ This component is still in development and is not yet stable for production. ⚠️

## Getting Started

```shell
  npm i svelte-meta-data
```

Simple example with basic site meta data

```svelte
<script>
  import SiteInfo from 'svelte-meta-data';

  const site_info = {
    site_url: "https://example.com",
    site_author: "Author Name",
    site_index: "/index",
  };
</script>

<SiteInfo {site_info}/>
```

*more examples to come*

Current Features include...

- [x] Global writable store to referance site meta data anywhere in your app 🌐
- [x] Automated creation of meta tags for SEO 🔎

Roadmap 🚗...

- [ ] Add ability to create page specific seo info similar to [svelte-seo](https://github.com/artiebits/svelte-seo)
- [ ] Convert to TypeScript

## Properties List

pass an object named "meta_data" to the component via props with any of the following key/value pairs. All data is optional

| Property                           | Type                    | Description              |
| ---------------------------------- | ----------------------- | ------------------------ |
| `title`                            | string                  | Sets the page meta title.|
| `description`                      | string                  | Sets the page meta description.|
| `noindex`                          | boolean (default false) | Sets whether page should be indexed or not.|
| `nofollow`                         | boolean (default false) | Sets whether page should be followed or not.|
| `keywords`                         | string                  | Set the page keywords.|
| `canonical`                        | string                  | Set the page canonical url.|
| `openGraph.title`                  | string                  | The open graph title, this can be different than your meta title.|
| `openGraph.description`            | string                  | The open graph description, this can be different than your meta description.|
| `openGraph.url`                    | string                  | The canonical URL of your object that will be used as its permanent ID in the graph.|
| `openGraph.images`                 | array                   | An array of images (object) to be used as a preview. If multiple supplied you can choose one when sharing.|
| `twitter.site`                     | string                  | The Twitter @username the card should be attributed to.|
| `twitter.title`                    | string                  | A concise title for the related content. Note- iOS, Android: Truncated to two lines in timeline and expanded Tweet ; Web: Truncated to one line in timeline and expanded Tweet.|
| `twitter.description`              | string                  | A description that concisely summarizes the content as appropriate for presentation within a Tweet. You should not re-use the title as the description or use this field to describe the general services provided by the website. Note- iOS, Android: Not displayed ; Web: Truncated to three lines in timeline and expanded Tweet                  |
| `twitter.image`                    | string(url)             | A URL to a unique image representing the content of the page. Images for this Card support an aspect ratio of 2:1 with minimum dimensions of 300x157 or maximum of 4096x4096 pixels. Images must be less than 5MB in size. JPG, PNG, WEBP and GIF formats are supported. Only the first frame of an animated GIF will be used. SVG is not supported. |
| `twitter.imageAlt`                 | string                  | A text description of the image conveying the essential nature of an image to users who are visually impaired. Maximum 420 characters.
