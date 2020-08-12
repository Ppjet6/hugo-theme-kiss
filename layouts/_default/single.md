---
title: "{{ .Title }}"
date: {{ .PublishDate }}
{{- if .Draft }}
draft: true
{{- end }}
permalink: {{ .Permalink }}index.md
htmlPermalink: {{ .Permalink }}
{{ if .Params.tags -}}
tags: [
  {{- range first 1 .Params.tags }} "{{ . }}"{{ end }}
  {{- if gt (len .Params.tags) 1 }}
    {{- range after 1 .Params.tags }}, "{{ . }}"{{ end }}
  {{- end }} ]
{{- end }}
---

{{ .RawContent }}
