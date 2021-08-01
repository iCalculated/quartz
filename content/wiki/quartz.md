---
title: "Quartz"
---

# [Quartz](https://quartz.jzhao.xyz/])

Used to publish Obsidian vaults without paying 4 USD/month.

Built on [Hugo](wiki/hugo.md), pages live in the `content` directory so I just symlinked my vault.

Home page lives in `content/_index.md` by default.

Colors can be edited in `assets/custom.scss`.

Image links should be prefixed with `/`. (untested)

## Customization

Graph view customization in `data/graphConfig.yaml`

```yaml
enableLegend: false # automatically generate a legend
enableDrag: true # allow dragging nodes in the graph
enableZoom: true # allow zooming and panning the graph
paths: # colour specific nodes path off of their path
  - /moc: "#4388cc"
```

Custom CSS in `assets/custom.scss` (or `style.scss`). Can add HTML partials in `/layouts/partials`.

### Partials

Structure of the home page can be changed in `/layouts/index.html`, footer specifically at `/layouts/partials/footer.html`.

Resource: [Hugo's website.](https://gohugo.io/templates/partials/)