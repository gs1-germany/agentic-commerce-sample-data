# Data Licensing Notice for Product Master Data Files (`*.jsonld`)

## Human-Readable Declaration

The factual product information contained in these files (e.g. GTIN, dimensions, ingredients)
originates from and remains the property of the respective **brand owner**. The files were
technically transformed (mapped, restructured, partially extended and partially reduced) from
source data supplied by a third-party solution provider. GS1 Germany claims **no rights over the
underlying factual content**.

> With the brand owner's consent, the product master data files are made available under
> **[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)**, which explicitly extends to any
> applicable sui generis database rights (Section 4, CC BY 4.0 Legal Code). Share-Alike
> obligations are deliberately avoided to keep the data friction-free for downstream (agentic)
> reuse, caching and aggregation.

## Machine-Readable Declaration

⚠️ Do not attach a bare `"license": "..."` directly onto a `gs1:Product` node — `dct:license` /
`schema:license` is only defined for `CreativeWork`-type nodes (e.g. `Dataset`), not `Product`.
The declaration below therefore applies at dataset level and covers all distributions:

```json
{
  "@context": {
    "dcat": "http://www.w3.org/ns/dcat#",
    "dct": "http://purl.org/dc/terms/"
  },
  "@id": "https://raw.githubusercontent.com/gs1-germany/agentic-commerce-sample-data/main/catalog.jsonld",
  "@type": "dcat:Dataset",
  "dct:title": "Agentic Commerce – Sample Product Master Data",
  "dct:license": "https://creativecommons.org/licenses/by/4.0/",
  "dcat:distribution": [
    {
      "@id": "https://raw.githubusercontent.com/gs1-germany/agentic-commerce-sample-data/main/catalog.jsonld#example-product-01",
      "@type": "dcat:Distribution",
      "dct:title": "Example Product 01",
      "dct:format": "application/ld+json",
      "dcat:downloadURL": "https://raw.githubusercontent.com/gs1-germany/agentic-commerce-sample-data/main/data/9987.jsonld"
    },
    {
      "@id": "https://raw.githubusercontent.com/gs1-germany/agentic-commerce-sample-data/main/catalog.jsonld#example-product-02",
      "@type": "dcat:Distribution",
      "dct:title": "Example Product 02",
      "dct:format": "application/ld+json",
      "dcat:downloadURL": "https://raw.githubusercontent.com/gs1-germany/agentic-commerce-sample-data/main/data/656565.jsonld"
    }
  ]
}
```

Note: `@id` values here use the raw GitHub URL as a stable, dereferenceable identifier for the
Dataset itself and a `#fragment` per Distribution — this avoids blank nodes and makes each
entity individually addressable (e.g. in the JSON-LD Playground, SPARQL queries, or by other
catalogs that want to link to a specific distribution).
