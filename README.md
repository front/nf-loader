# nf-loader
Provides  methods for lazy and media-aware content loading.

### nfLoadAware

Loads a chunk of html based on a css media-query. Receives an array with a set of media queries and specific targets.

`query` - the css media-query to match

`target` - the uri of the resource to be loaded into the element

```
$('.add-space').nfLoadAware([
{
   	query: 'screen and (max-width:480px)',
	target: './res/ad_small.html'
}, {
	query: 'screen and (min-width:481px) and (max-width:800px)',
	target: './res/ad_medium.html'
}, {
	query: 'screen and (min-width:801px)',
	target: './res/ad_large.html'
}
]);
```

### nfLazyLoad 

Lazily loads a chunk of html.

`offset` - the number of pixels below the bottom of the viewport, when the load is triggered.

`target` -  the uri of the resource to be loaded into the element

```
$('.lazy-content').nfLazyLoad({
	offset: 200,
	target: './res/lazy-content.html'
});
```

### nfLazyImage

Lazily loads a image (requires an `img-src` field on the target element).

`offset` - the number of pixels below the bottom of the viewport, when the load is triggered.

```
$('.lazy-image').nfLazyImage({
	offset: 400
});
```

### nfLazyLoadAware

Lazily loads a chunk of html based on a css media-query. An combination of `nfLoadAware` and `nfLazyLoad` methods. 

`query` - the css media-query to match

`target` - the uri of the resource to be loaded into the element

`offset` - the number of pixels below the bottom of the viewport, when the load is triggered. 

```
$('.lazy-aware').nfLazyLoadAware([
	{
		query: 'screen and (min-width:801px)',
		target: './res/ferrari.html'
	}, {
		query: 'screen and (max-width:800px)',
		target: './res/fiat.html'
	}
	],{
		offset: 500
	}
);
```

## Demo

[http://front.github.io/nf-loader/](http://front.github.io/nf-loader/)

## Dependencies

#### enquire.js 

enquire.js is a lightweight, pure JavaScript library for responding to CSS media queries.

[http://wicky.nillia.ms/enquire.js/](http://wicky.nillia.ms/enquire.js/)

LICENSE: [https://github.com/WickyNilliams/enquire.js/](https://github.com/WickyNilliams/enquire.js/)

#### waypoints

Waypoints is a jQuery plugin that makes it easy to execute a function whenever you scroll to an element.

[http://imakewebthings.com/jquery-waypoints/](http://imakewebthings.com/jquery-waypoints/)

LICENSE: [https://github.com/imakewebthings/jquery-waypoints/blob/master/licenses.txt](https://github.com/imakewebthings/jquery-waypoints/blob/master/licenses.txt)

## License

[MIT](https://github.com/front/nf-loader/blob/master/LICENSE)