# Delphi Daily Astro Blog

Clean Medium-style Astro blog template for **DelphiDaily.com**.

## What is included

- Astro 5 project
- Clean editorial design
- Blog archive
- Blog post page
- About page
- RSS feed
- Sitemap integration
- Working Shiki syntax highlighting
- Pascal code fences for Delphi examples

## Run locally

```powershell
npm.cmd install
npm.cmd run dev
```

Open:

```text
http://localhost:4321
```

## Build

```powershell
npm.cmd run build
npm.cmd run preview
```

## Important: Delphi code highlighting

Use `pascal` instead of `delphi` in Markdown code fences:

````md
```pascal
procedure TMainForm.Button1Click(Sender: TObject);
begin
  ShowMessage('Hello');
end;
```
````

The global CSS intentionally does not override `.astro-code span` colors, so Shiki token colors stay visible.

## Deploy to Vercel

Recommended settings:

```text
Framework Preset: Astro
Root Directory: ./
Build Command: npm run build
Output Directory: dist
Install Command: empty / auto
```
