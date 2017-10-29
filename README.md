# deck.gl + react-map-gl + GeoJSON

This is based off the [GeoJSON example in the deck.gl repo](https://github.com/uber/deck.gl/blob/master/examples/geojson/app.js)

If you [look at the timeline where I loaded & refreshed 3 times](https://chromedevtools.github.io/timeline-viewer/?loadTimelineFromURL=https://cdn.glitch.com/38402265-c018-45c8-a96f-a1626887e9eb%2Fabout-blank-to-silver-saxophone.glitch.me-soft-refresh-x2-hard-refresh-20171023T103321.json?1508781329730), you can see the ~3 sec pauses on `getProgramParameter`
![this timeline](https://cdn.glitch.com/38402265-c018-45c8-a96f-a1626887e9eb%2Fsilver-saxophone.glitch.me-timeline.png?1508781168506)

Since this looks like it's from WebGL or one of `deck.gl`, `react-map-gl` or `mapbox-gl-js`, I'm not sure how to improve the performance, but I realized [the GeoJSON file](https://gist.githubusercontent.com/jfsiii/b031dbbe7385d2c6822468a001d62225/raw/8ad146ac7db178b82480b8eb46eaaf406f60dc5d/USA-boundaries.json) is pretty large (~3MB) so I simplified the file down to ~30k but that just moved the ~3 sec pauses to a different function. ![other timeline](https://cdn.glitch.com/eb8c029b-6783-4bcd-87fe-df6b46584e00%2Freminiscent-glue.glitch.me-timeline.png?1508781957386)

See the [demo](reminiscent-glue.glitch.me) ([code](https://glitch.com/edit/#!/reminiscent-glue?path=client/App.js:1:0)) which uses the 30K file
