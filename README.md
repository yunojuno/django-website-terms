# django-website-terms

Django app for managing website terms and conditions

Website terms change over time. This app is designed to allow site owners to update terms in advance, make terms active on a specific date, and to track user acceptance of terms.

### Assumptions

Terms are static

### Use cases:

* As a website admin I want to be able to update terms
* As a website admin I want to be able to publish terms on a given date
* As a website admin I want to ensure that users see the correct terms
* As a website admin I want to ensure that users have accepted terms
* As a website admin I want to record when users have accepted terms
* As a user I want to be sure the correct terms apply
* As a user I can accept multiple terms (e.g. privacy, Ts&Cs, ...) at the same time

### Models 

```yaml
WebsiteTerms:
  category: str ["privacy", "website_use", "..."]
  version: int
  effective_from: date
  document_type: str ["HTML", "PDF"]
  document_url: url

UserTerms:
  user: User
  terms: WebsiteTerms
  accepted_at: datetime
```
