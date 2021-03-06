set(cairo_headers cairo.h cairo-deprecated.h)
set(cairo_private
    cairoint.h
    cairo-analysis-surface-private.h
    cairo-arc-private.h
    cairo-array-private.h
    cairo-atomic-private.h
    cairo-backend-private.h
    cairo-box-inline.h
    cairo-boxes-private.h
    cairo-cache-private.h
    cairo-clip-inline.h
    cairo-clip-private.h
    cairo-combsort-inline.h
    cairo-compiler-private.h
    cairo-compositor-private.h
    cairo-contour-inline.h
    cairo-contour-private.h
    cairo-composite-rectangles-private.h
    cairo-damage-private.h
    cairo-default-context-private.h
    cairo-device-private.h
    cairo-error-inline.h
    cairo-error-private.h
    cairo-fixed-private.h
    cairo-fixed-type-private.h
    cairo-freelist-private.h
    cairo-freelist-type-private.h
    cairo-freed-pool-private.h
    cairo-fontconfig-private.h
    cairo-gstate-private.h
    cairo-hash-private.h
    cairo-image-info-private.h
    cairo-image-surface-inline.h
    cairo-image-surface-private.h
    cairo-line-inline.h
    cairo-line-private.h
    cairo-list-inline.h
    cairo-list-private.h
    cairo-malloc-private.h
    cairo-mempool-private.h
    cairo-mutex-impl-private.h
    cairo-mutex-list-private.h
    cairo-mutex-private.h
    cairo-mutex-type-private.h
    cairo-output-stream-private.h
    cairo-paginated-private.h
    cairo-paginated-surface-private.h
    cairo-path-fixed-private.h
    cairo-path-private.h
    cairo-pattern-inline.h
    cairo-pattern-private.h
    cairo-pixman-private.h
    cairo-private.h
    cairo-recording-surface-inline.h
    cairo-recording-surface-private.h
    cairo-reference-count-private.h
    cairo-region-private.h
    cairo-rtree-private.h
    cairo-scaled-font-private.h
    cairo-slope-private.h
    cairo-spans-private.h
    cairo-spans-compositor-private.h
    cairo-stroke-dash-private.h
    cairo-surface-inline.h
    cairo-surface-private.h
    cairo-surface-backend-private.h
    cairo-surface-clipper-private.h
    cairo-surface-fallback-private.h
    cairo-surface-observer-inline.h
    cairo-surface-observer-private.h
    cairo-surface-offset-private.h
    cairo-surface-subsurface-inline.h
    cairo-surface-subsurface-private.h
    cairo-surface-snapshot-inline.h
    cairo-surface-snapshot-private.h
    cairo-surface-wrapper-private.h
    cairo-time-private.h
    cairo-types-private.h
    cairo-traps-private.h
    cairo-tristrip-private.h
    cairo-user-font-private.h
    cairo-wideint-private.h
    cairo-wideint-type-private.h
    )
set(cairo_sources
    cairo-analysis-surface.c
    cairo-arc.c
    cairo-array.c
    cairo-atomic.c
    cairo-base64-stream.c
    cairo-base85-stream.c
    cairo-bentley-ottmann.c
    cairo-bentley-ottmann-rectangular.c
    cairo-bentley-ottmann-rectilinear.c
    cairo-botor-scan-converter.c
    cairo-boxes.c
    cairo-boxes-intersect.c
    cairo.c
    cairo-cache.c
    cairo-clip.c
    cairo-clip-boxes.c
    cairo-clip-polygon.c
    cairo-clip-region.c
    cairo-clip-surface.c
    cairo-color.c
    cairo-composite-rectangles.c
    cairo-compositor.c
    cairo-contour.c
    cairo-damage.c
    cairo-debug.c
    cairo-default-context.c
    cairo-device.c
    cairo-error.c
    cairo-fallback-compositor.c
    cairo-fixed.c
    cairo-font-face.c
    cairo-font-face-twin.c
    cairo-font-face-twin-data.c
    cairo-font-options.c
    cairo-freelist.c
    cairo-freed-pool.c
    cairo-gstate.c
    cairo-hash.c
    cairo-hull.c
    cairo-image-compositor.c
    cairo-image-info.c
    cairo-image-source.c
    cairo-image-surface.c
    cairo-line.c
    cairo-lzw.c
    cairo-matrix.c
    cairo-mask-compositor.c
    cairo-mesh-pattern-rasterizer.c
    cairo-mempool.c
    cairo-misc.c
    cairo-mono-scan-converter.c
    cairo-mutex.c
    cairo-no-compositor.c
    cairo-observer.c
    cairo-output-stream.c
    cairo-paginated-surface.c
    cairo-path-bounds.c
    cairo-path.c
    cairo-path-fill.c
    cairo-path-fixed.c
    cairo-path-in-fill.c
    cairo-path-stroke.c
    cairo-path-stroke-boxes.c
    cairo-path-stroke-polygon.c
    cairo-path-stroke-traps.c
    cairo-path-stroke-tristrip.c
    cairo-pattern.c
    cairo-pen.c
    cairo-polygon.c
    cairo-polygon-intersect.c
    cairo-polygon-reduce.c
    cairo-raster-source-pattern.c
    cairo-recording-surface.c
    cairo-rectangle.c
    cairo-rectangular-scan-converter.c
    cairo-region.c
    cairo-rtree.c
    cairo-scaled-font.c
    cairo-shape-mask-compositor.c
    cairo-slope.c
    cairo-spans.c
    cairo-spans-compositor.c
    cairo-spline.c
    cairo-stroke-dash.c
    cairo-stroke-style.c
    cairo-surface.c
    cairo-surface-clipper.c
    cairo-surface-fallback.c
    cairo-surface-observer.c
    cairo-surface-offset.c
    cairo-surface-snapshot.c
    cairo-surface-subsurface.c
    cairo-surface-wrapper.c
    cairo-time.c
    cairo-tor-scan-converter.c
    cairo-tor22-scan-converter.c
    cairo-clip-tor-scan-converter.c
    cairo-toy-font-face.c
    cairo-traps.c
    cairo-tristrip.c
    cairo-traps-compositor.c
    cairo-unicode.c
    cairo-user-font.c
    cairo-version.c
    cairo-wideint.c
    )

add_library(cairo
    ${cairo_headers}
    ${cairo_private}
    ${cairo_sources})

target_link_libraries(cairo
    ${PIXMAN_LIBRARY})

if(NOT BUILD_SHARED_LIBS)
    target_compile_definitions(cairo
        PUBLIC -DCAIRO_WIN32_STATIC_BUILD)
endif()
