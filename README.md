# more.js

## Overview

more.js is a small and simple jQuery plugin that makes having a button to fetch additional resources a breeze. more.js
enables developers to easily implement something similar to the GitHub "more" button on the dashboard.

![GitHub more](http://i.imgur.com/psjMfQH.png)

## Getting Started

more.js is stupid simple. 

### What you need:

* Element selector for your "more" button. (eg. "#more-btn")
* A URL to fetch more resources from.
* Element selector to populate resources with. (eg. "#resources-table")
* Function to build HTML from returned data.

### Optional:

* Input field to get a query string from when fetching resources.
* Twitter Bootstrap "button" plugin to enable the "loading" functionality (recommended)

## Example

(with optional bootstrap)

```html
<html>
    <body>
        <table id="resources-table">
            ...
        </table>
        <button id="more-btn" class="btn btn-default btn-lg btn-block" 
                                    data-loading-text="Loading&hellip;">
            More
        </button>
        <script>
        var currentPage = 1; // This MUST be defined

        $("#more-btn").more({
            url: "http://example.com/resources/json",
            table: "#resources-table",
            queryParam: 'query', // default to 'q'
            pageParam: 'p', // defaults to 'page'
            dataType: 'xml', // defaults to 'json'
            bootstrap: true, // defaults to false

            buildEntries: function() {
                var html = ...
                return html;
            }
        });
        </script>
    </body>
</html>
```

## License

more.js is licensed under the MIT License. The full text can be found in the [LICENSE.md](LICENSE.md)
