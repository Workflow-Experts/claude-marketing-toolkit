# Schema Markup Examples

Ready-made JSON-LD templates for the most common schema types. When the user needs schema markup, start with the relevant template below and populate it with their actual information.

Always remind the user to:
1. Place the JSON-LD in a `<script type="application/ld+json">` tag in the `<head>` section or before `</body>`
2. Test with Google's Rich Results Test (https://search.google.com/test/rich-results) after implementation
3. Make sure the schema matches the visible page content exactly

---

## LocalBusiness

Use for any business with a physical location or defined service area. Replace LocalBusiness with a more specific type where one exists (e.g., Dentist, Plumber, Restaurant, LegalService, FinancialService).

```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "Business Name",
  "description": "Brief description of the business and what it does.",
  "url": "https://www.example.com",
  "telephone": "+44-XXXX-XXXXXX",
  "email": "info@example.com",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 High Street",
    "addressLocality": "Manchester",
    "addressRegion": "Greater Manchester",
    "postalCode": "M1 1AA",
    "addressCountry": "GB"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "53.4808",
    "longitude": "-2.2426"
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "17:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "09:00",
      "closes": "13:00"
    }
  ],
  "areaServed": [
    {
      "@type": "City",
      "name": "Manchester"
    },
    {
      "@type": "City",
      "name": "Salford"
    }
  ],
  "priceRange": "££",
  "image": "https://www.example.com/images/business-photo.jpg",
  "sameAs": [
    "https://www.facebook.com/businessname",
    "https://www.instagram.com/businessname"
  ]
}
```

---

## FAQPage

Use for any page with question-and-answer content. Each question-answer pair must be visible on the page.

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What does your service include?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Our service includes X, Y, and Z. We also provide ongoing support and maintenance as part of every package."
      }
    },
    {
      "@type": "Question",
      "name": "How much does it cost?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Pricing starts from £X per month. Contact us for a personalised quote based on your requirements."
      }
    },
    {
      "@type": "Question",
      "name": "How long does it take?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Most projects are completed within 2-4 weeks depending on scope and complexity."
      }
    }
  ]
}
```

---

## Article / BlogPosting

Use for blog posts and articles. BlogPosting is a more specific subtype of Article and is generally preferred for blog content.

```json
{
  "@context": "https://schema.org",
  "@type": "BlogPosting",
  "headline": "Article Title Here (max 110 characters)",
  "description": "Brief summary of the article content.",
  "url": "https://www.example.com/blog/article-slug",
  "datePublished": "2026-01-15",
  "dateModified": "2026-03-20",
  "author": {
    "@type": "Person",
    "name": "Author Name",
    "url": "https://www.example.com/about/author-name"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Business Name",
    "logo": {
      "@type": "ImageObject",
      "url": "https://www.example.com/images/logo.png"
    }
  },
  "image": "https://www.example.com/images/article-featured-image.jpg",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://www.example.com/blog/article-slug"
  }
}
```

---

## HowTo

Use for step-by-step guides and tutorials. Each step must match visible content on the page.

```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "How to [Do the Thing]",
  "description": "A step-by-step guide to [doing the thing].",
  "totalTime": "PT30M",
  "estimatedCost": {
    "@type": "MonetaryAmount",
    "currency": "GBP",
    "value": "0"
  },
  "step": [
    {
      "@type": "HowToStep",
      "name": "Step 1 title",
      "text": "Detailed instruction for step 1.",
      "url": "https://www.example.com/guide#step-1",
      "image": "https://www.example.com/images/step-1.jpg"
    },
    {
      "@type": "HowToStep",
      "name": "Step 2 title",
      "text": "Detailed instruction for step 2.",
      "url": "https://www.example.com/guide#step-2",
      "image": "https://www.example.com/images/step-2.jpg"
    },
    {
      "@type": "HowToStep",
      "name": "Step 3 title",
      "text": "Detailed instruction for step 3.",
      "url": "https://www.example.com/guide#step-3",
      "image": "https://www.example.com/images/step-3.jpg"
    }
  ]
}
```

---

## Product

Use for product pages with pricing information.

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Product Name",
  "description": "Brief product description.",
  "url": "https://www.example.com/products/product-name",
  "image": "https://www.example.com/images/product.jpg",
  "brand": {
    "@type": "Brand",
    "name": "Brand Name"
  },
  "offers": {
    "@type": "Offer",
    "price": "99.99",
    "priceCurrency": "GBP",
    "availability": "https://schema.org/InStock",
    "url": "https://www.example.com/products/product-name"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.5",
    "reviewCount": "42"
  }
}
```

Only include aggregateRating if the page displays real reviews. Do not fabricate ratings.

---

## Service

Use for service description pages.

```json
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Service Name",
  "description": "What this service includes and who it's for.",
  "url": "https://www.example.com/services/service-name",
  "provider": {
    "@type": "LocalBusiness",
    "name": "Business Name",
    "url": "https://www.example.com"
  },
  "areaServed": {
    "@type": "City",
    "name": "Manchester"
  },
  "serviceType": "Category of Service"
}
```

---

## BreadcrumbList

Use for site navigation breadcrumbs. Helps search engines understand site structure.

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://www.example.com"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Services",
      "item": "https://www.example.com/services"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Service Name",
      "item": "https://www.example.com/services/service-name"
    }
  ]
}
```

---

## Organization

Use on the about page or homepage for company-level information.

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Business Name",
  "url": "https://www.example.com",
  "logo": "https://www.example.com/images/logo.png",
  "description": "Brief description of the organisation.",
  "foundingDate": "2020",
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+44-XXXX-XXXXXX",
    "contactType": "customer service",
    "availableLanguage": "English"
  },
  "sameAs": [
    "https://www.facebook.com/businessname",
    "https://www.instagram.com/businessname",
    "https://www.linkedin.com/company/businessname"
  ]
}
```

---

## Combining Multiple Schema Types

Pages often benefit from more than one schema type. For example, a local plumber's blog post about fixing a leaking tap might use:

- **BlogPosting** for the article itself
- **HowTo** for the step-by-step instructions within it
- **LocalBusiness** sitewide or on the page if it includes business contact details

Multiple schemas can coexist on the same page. Place each in its own `<script type="application/ld+json">` tag, or combine them in a single tag using the `@graph` property:

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "BlogPosting",
      "headline": "How to Fix a Leaking Tap",
      "...": "..."
    },
    {
      "@type": "HowTo",
      "name": "How to Fix a Leaking Tap",
      "...": "..."
    }
  ]
}
```

Use `@graph` when the schemas are related to the same page. Use separate script tags if they represent different entities.
