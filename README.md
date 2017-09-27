# Trinity
Trinity is a less library for handling reponsive breakpoints of devices
and frameworks painlessly.

## Table of contents
* [Installation](#installation)
  * [webpack](#webpack)
  * [Other build engines](#other)
* [Usage](#usage)
  * [General](#general)
  * [Min-width breakpoints](#minwidth)
  * [Custom breakpoints](#custom)
* [Devices and breakpoints](#devices)
  * [Mobile](#mobile)
  * [Tablet](#tablet)
  * [Desktop](#desktop)
  * [Bootstrap](#bootstrap)
* [Todo](#todo)
* [Contributing](#contributing)
* [License](#license)

## Installation
Trinity can be installed via npm. Simply type:
```
npm i -S @shopmacher/trinity
```

After installing trinity, you can integrate it in your project depending
on what build engine you use.

### webpack
If you use webpack as your build engine, make sure you have a
[less-loader]() set up. Then you can include trinity either in your
less file using
```css
@import '~@shopmacher/trinity/lib/trinity.less';
```

### [Other build engines](#other)
For any other build engine besides webpack, make sure to include the
following file in your less bundle:
```
node_modules/@shopmacher/trinity/lib/trinity.less
```

## Usage
Trinity provides a set of breakpoints and mixins for different screen
sizes and UI frameworks. This section shows, how to use the trinity
mixins for the different devices.

### General
All mixins are used in a similar way, which is:
```less
.device({
    // Styles for the device here
});
```

Simply replace `device` with a device from one of the
[devices-sections](#devices) below,
as in this example for a mobile device in landscape orientation:
```less
.mobile-landscape({
    // Mobile landscape styles here
});
```

If you do not want to use the mixins, you always have the option to
use the `@media` keyword in conjunction with the breakpoints.

```less
@media @mobile {
    // Mobile styles here
}
```

### [Min-width mixins](#minwidth)
In some cases, you want to provide style for a specific screen size and
all above that one. For example: mobile and above. For this, trinity
allows you to add the `-up` suffix, to every mixin available including
orientations.

```less
.mobile-up({
    // This styles mobile and larger devices (tablet, desktop)
)}
```

### [Custom breakpoints](#custom)
If the built-in breakpoints are not sufficient for you, there is a mixin
to use custom breakpoints.

```less
@min: 300px;
@max: 500px;

.responsive(@min, @max, {
    // This styles devices from @min to @max width
});

.reponsive(@min, {
    // This styles devices from @min width and up
});
```

## [Devices and breakpoints](#devices)
The following tables show the different built-in devices and breakpoints.

### Mobile

| Device            | min-width  | max-width  |
|-----------------|----------:|----------:|
| mobile            | mobile-min | mobile-max |
| mobile-portrait   | "          | "          |
| mobile-landscape  | "          | "          |

| Breakpoint | Value   |
|-----------|-------:|
| mobile-min | 320px   |
| mobile-max | 480px   |

### Tablet

| Device            | min-width  | max-width  |
|-----------------|----------:|----------:|
| tablet            | tablet-min | tablet-max |
| tablet-portrait   | "          | "          |
| tablet-landscape  | "          | "          |

| Breakpoint | Value   |
|-----------|-------:|
| tablet-min | 768px   |
| tablet-max | 1024px  |

### Desktop

| Device            | min-width  | max-width  |
|-----------------|----------:|----------:|
| desktop           | desktop-min| -          |

| Breakpoint  | Value   |
|------------|-------:|
| desktop-min | 1025px   |

### Bootstrap

If you use the bootstrap framework, you can use the following breakpoints
as they reflect the ones bootstrap uses.

| Mixin             | min-width  | max-width  |
|-----------------|----------:|----------:|
| xs                | 0          | xs-max     |
| sm                | sm-min     | sm-max     |
| md                | md-min     | md-max     |
| lg                | lg-min     | -          |

| Breakpoint | Value   |
|-----------|-------:|
| xs-max     | 768px   |
| sm-min     | 769px   |
| sm-max     | 991px   |
| md-min     | 992px   |
| md-max     | 1199px  |
| lg-min     | 1200px  |

## Todo
- [x] Implement generic mobile, tablet and desktop devices
- [x] Implement bootstrap breakpoints
- [x] Document usage
- [ ] Provide examples
- [ ] Add specific devices, like iPhones
- [ ] Add support for em media queries

## Contributing
In order to make contributions to the project, fork the project and
create a feature/hotfix branch with the contribution you want to make.

When you finished developing, document the changes and submit a pull
request.

Of course, you can always submit issues for bugs or feature-requests.

## License
MIT
