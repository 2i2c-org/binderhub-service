# Helm chart repository for binderhub-service</title>
This is a bare Helm chart repository specifically for the binderhub-service chart.

For more information, visit the [project's documentation](https://binderhub-service.readthedocs.io/).

## Releases

{% for chartmap in site.data.index.entries %}
| Version | Date | App. version |
|---------|------|---------------------|
  {%- assign sortedcharts = chartmap[1] | sort: 'created' | reverse -%}
  {%- for chart in sortedcharts -%}
    {%- unless chart.version contains "-" %} | [{{ chart.version }}]({{ chart.urls[0] }}) | {{ chart.created | date_to_long_string }} | {{ chart.appVersion }} |
    {%- endunless -%}
  {%- endfor %}
{% endfor %}
