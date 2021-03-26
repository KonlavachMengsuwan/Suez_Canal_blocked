# Suez_Canal_blocked

## Since 23th March Ever Given contaner ship blocking the Suez Canal

## Let's explore the site with High Resolution Satellite imagery: 4-band PlanetScope, Planet Lab 
## Thanks to Planet's Education and Research Program from Planet Lab

## 1. Load "raster" library
```
library(raster)
```

## 2. Read GeoTiff file
```
suez_canal = stack("20210325_081016_1011_3B_AnalyticMS.tif")
```

## 3. Draw Extent
```
e <- drawExtent()
```

## 4. Crop image
```
cropped_suez_canal <- crop(suez_canal,e)
```

## 5. Combine RGB bands
```
suez_canalRGB = stack(list(cropped_suez_canal[[3]], cropped_suez_canal[[2]], cropped_suez_canal[[1]]))
```

## 6. Plot RGB
```
plotRGB(suez_canalRGB, axes = FALSE, stretch = "lin", main = "4-band PlanetScope 3m-resolution", xaxt = 'n', yaxt = 'n')
```

## 7. Export Image
```
png('1.png', width = 4, height = 5, units = "in", res = 300)
plotRGB(suez_canalRGB, axes = FALSE, stretch = "lin", main = "4-band PlanetScope 3m-resolution", xaxt = 'n', yaxt = 'n')
dev.off()
```

