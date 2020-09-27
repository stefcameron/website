# Home

Personal website home page.

## Jekyll

Built with https://jekyllrb.com/

### Local Development

```bash
$ cd home
$ jekyll server
```

Open your browser to http://localhost:4000

### Publishing

Build the site in `production` mode:

```bash
$ cd home
$ JEKYLL_ENV=production jekyll build
```

Then `rsync` or `scp` up to the web server:

```bash
$ cd home
$ rsync -azPr _site/ user@host:site.com/
```
