# "Headers and Footers": Chapbook (v1.0.0)

## Summary

Chapbook provides two global variables, [`config.header` and `config.footer`](https://klembot.github.io/chapbook/guide/customization/header-and-footer.html), that each have the properties `left`, `right`, and `center`. When set, these properties show their content as the header or footer in the particular position matching its property name.

## Live Example

<section>
<iframe src="chapbook_headersandfooters_example.html" height=400 width=90%></iframe>

Download: <a href="chapbook_headersandfooters_example.html" target="_blank">Live Example</a>
</section>

## Twee Code

```
:: StoryTitle
Chapbook: Header and Footer

:: Start
config.header.center: "This is the header!"
config.footer.center: "This is the footer!"
--
This is content.

```

Download: <a href="chapbook_headersandfooters_twee.txt" target="_blank">Twee Code</a>
