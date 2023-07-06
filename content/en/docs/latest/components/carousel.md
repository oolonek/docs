---
author: Mark Dumay
title: Carousel
date: 2023-05-21
description: Use the carousel shortcode to display a carousel of several images.
layout: docs
icon: fas images
tags: component
---

## Overview

{{< release version="v0.7.1" >}}

Use the `carousel` shortcode to display a carousel of several images, with similar behavior as the [image]({{< ref "image" >}} "image"). As an example, the following shortcode displays a centered carousel with three slides, 16x9 aspect ratio, and a relative width of 67% on large screens.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* carousel ratio="16x9" class="col-sm-12 col-lg-8 mx-auto" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 1" */>}}
  {{</* img src="img/phone.jpg" caption="slide 2" */>}}
  {{</* img src="img/dunes.jpg" caption="slide 3" */>}}
{{</* /carousel */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

## Arguments

The carousel shortcode supports the following arguments:

{{< table >}}
| Argument  | Required | Description |
|-----------|----------|-------------|
| id        | No  | Optional id of the carousel, defaults to "carousel-n" with a sequential number `n`. |
| ratio     | No  | Aspect ratio of the image, either "1x1", "4x3", "16x9", or "21x9". If unspecified, the original aspect ratio is preserved. |
| class     | No  | Optional class attribute of the `carousel` element, e.g. "w-75". |
{{< /table >}}

{{< alert >}}
The carousel uses the original aspect ratio of the provided images when no aspect ratio is provided. Ensure the included images have a similar height and width to avoid inconsistent behavior.
{{< /alert >}}

Add an inner `img` element for each slide of the carousel. The `img` element supports the following arguments:

{{< table >}}
| Argument  | Required | Description |
|-----------|----------|-------------|
| src       | Yes | Required url of the image, e.g. "img/boots.jpg". |
| caption   | No  | Optional image caption. If set, the image is darkened to improve the contrast. The caption is hidden on smaller screens. |
{{< /table >}}

## Examples

As an example, the following shortcodes display a centered carousel with three slides, 16x9 aspect ratio, and a relative width of 67% on large screens.

Set the `ratio` to `1x1` for a square aspect ratio.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* carousel id="carousel-1x1" ratio="1x1" class="col-sm-12 col-lg-6 mx-auto" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 1" */>}}
  {{</* img src="img/phone.jpg" caption="slide 2" */>}}
  {{</* img src="img/dunes.jpg" caption="slide 3" */>}}
{{</* /carousel */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

Set the `ratio` to `4x3` for a landscape aspect ratio.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* carousel id="carousel-4x3" ratio="4x3" class="col-sm-12 col-lg-8 mx-auto" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 1" */>}}
  {{</* img src="img/phone.jpg" caption="slide 2" */>}}
  {{</* img src="img/dunes.jpg" caption="slide 3" */>}}
{{</* /carousel */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

Set the `ratio` to `16x9` for a landscape aspect ratio.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* carousel id="carousel-16x9" ratio="16x9" class="col-sm-12 col-lg-8 mx-auto" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 1" */>}}
  {{</* img src="img/phone.jpg" caption="slide 2" */>}}
  {{</* img src="img/dunes.jpg" caption="slide 3" */>}}
{{</* /carousel */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

Set the `ratio` to `21x9` for a landscape aspect ratio.

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* carousel id="carousel-21x9" ratio="21x9" class="col-sm-12 col-lg-8 mx-auto" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 1" */>}}
  {{</* img src="img/phone.jpg" caption="slide 2" */>}}
  {{</* img src="img/dunes.jpg" caption="slide 3" */>}}
{{</* /carousel */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->

Omit the `ratio` to keep the original aspect ratio.

{{< alert color="primary" >}}
    The carousel does not crop the images when omitting the aspect ratio. Instead, the images keep their original aspect ratio. Ensure the images have an equal aspect ratio to avoid layout shifting.
{{< /alert >}}

<!-- markdownlint-disable MD037 -->
{{< example lang="hugo" >}}
{{</* carousel id="carousel-original" class="col-sm-12 col-lg-8 mx-auto" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 1" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 2" */>}}
  {{</* img src="img/coffee.jpg" caption="slide 3" */>}}
{{</* /carousel */>}}
{{< /example >}}
<!-- markdownlint-enable MD037 -->