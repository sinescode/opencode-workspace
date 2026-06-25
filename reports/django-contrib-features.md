# Django 6.0.6 contrib Packages — Feature Comparison with Rjango

> **Django modules analyzed:** `django.contrib.admin`, `django.contrib.sessions`, `django.contrib.messages`, `django.contrib.staticfiles`, `django.contrib.sites`, `django.contrib.sitemaps`, `django.contrib.flatpages`, `django.contrib.redirects`, `django.contrib.humanize`, `django.contrib.contenttypes`, `django.contrib.syndication`, `django.contrib.postgres`, `django.contrib.admindocs`, `django.contrib.gis`

---

## SECTION 1: Admin (`django.contrib.admin`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class AdminSite` | `AdminSite` | ⚠️ Partial | Present in `rjango-admin` |
| `AdminSite.register(model_or_iterable, admin_class)` | `AdminSite::register()` | ✅ | |
| `AdminSite.unregister(model_or_iterable)` | ❌ Missing | |
| `AdminSite.get_urls()` | ❌ Missing | |
| `AdminSite.index(request)` | `AdminSite::index()` | ✅ | |
| `AdminSite.app_index(request, app_label)` | `AdminSite::app_index()` | ✅ | |
| `AdminSite.login(request)` | ❌ Missing | |
| `AdminSite.logout(request)` | ❌ Missing | |
| `AdminSite.password_change(request)` | ❌ Missing | |
| `AdminSite.password_change_done(request)` | ❌ Missing | |
| `AdminSite.each_context(request)` | ❌ Missing | |
| `AdminSite.index_template` | ❌ Missing | |
| `AdminSite.app_index_template` | ❌ Missing | |
| `AdminSite.login_template` | ❌ Missing | |
| `AdminSite.logout_template` | ❌ Missing | |
| `AdminSite.password_change_template` | ❌ Missing | |
| `AdminSite.password_change_done_template` | ❌ Missing | |
| `class ModelAdmin` (base admin class) | `ModelAdmin` | ⚠️ Partial | |
| `ModelAdmin.list_display` | `ModelAdmin::list_display` | ✅ | |
| `ModelAdmin.list_filter` | ❌ Missing | |
| `ModelAdmin.search_fields` | ❌ Missing | |
| `ModelAdmin.list_editable` | ❌ Missing | |
| `ModelAdmin.list_per_page` | ❌ Missing | |
| `ModelAdmin.ordering` | ❌ Missing | |
| `ModelAdmin.fieldsets` | ❌ Missing | |
| `ModelAdmin.fields` | ❌ Missing | |
| `ModelAdmin.exclude` | ❌ Missing | |
| `ModelAdmin.raw_id_fields` | ❌ Missing | |
| `ModelAdmin.readonly_fields` | ❌ Missing | |
| `ModelAdmin.prepopulated_fields` | ❌ Missing | |
| `ModelAdmin.autocomplete_fields` | ❌ Missing | |
| `ModelAdmin.filter_horizontal` | ❌ Missing | |
| `ModelAdmin.filter_vertical` | ❌ Missing | |
| `ModelAdmin.radio_fields` | ❌ Missing | |
| `ModelAdmin.save_as` | ❌ Missing | |
| `ModelAdmin.save_on_top` | ❌ Missing | |
| `ModelAdmin.inlines` | ❌ Missing | |
| `ModelAdmin.date_hierarchy` | ❌ Missing | |
| `ModelAdmin.actions` | ❌ Missing | |
| `ModelAdmin.action_form` | ❌ Missing | |
| `ModelAdmin.change_list_template` | ❌ Missing | |
| `ModelAdmin.change_form_template` | ❌ Missing | |
| `ModelAdmin.delete_confirmation_template` | ❌ Missing | |
| `ModelAdmin.object_history_template` | ❌ Missing | |
| `ModelAdmin.changelist_view(request)` | ✅ | |
| `ModelAdmin.changeform_view(request, object_id)` | ✅ | |
| `ModelAdmin.add_view(request)` | ✅ | |
| `ModelAdmin.delete_view(request, object_id)` | ✅ | |
| `ModelAdmin.history_view(request, object_id)` | ❌ Missing | |
| `ModelAdmin.get_queryset(request)` | ❌ Missing | |
| `ModelAdmin.get_ordering(request)` | ❌ Missing | |
| `ModelAdmin.get_search_results(request, queryset)` | ❌ Missing | |
| `ModelAdmin.save_model(request, obj, form, change)` | ❌ Missing | |
| `ModelAdmin.delete_model(request, obj)` | ❌ Missing | |
| `ModelAdmin.save_formset(request, form, formset, change)` | ❌ Missing | |
| `ModelAdmin.response_add(request, obj)` | ❌ Missing | |
| `ModelAdmin.response_change(request, obj)` | ❌ Missing | |
| `ModelAdmin.response_delete(request, obj)` | ❌ Missing | |
| `class InlineModelAdmin` | ❌ Missing | |
| `class StackedInline` | ❌ Missing | |
| `class TabularInline` | ❌ Missing | |
| `class DefaultAdminSite` (lazy singleton) | ❌ Missing | |
| `admin.site` (global instance) | `site` | ✅ | |
| `actions` module | ❌ Missing | delete_selected etc. |
| `helpers` module | ❌ Missing | |
| `checks` module | ❌ Missing | |
| `filters` module | ❌ Missing | |
| `forms` module | ❌ Missing | |
| `decorators: action, display, register` | ❌ Missing | |
| `class ShowFacets` | ❌ Missing | |
| `get_content_type_for_model(obj)` | ❌ Missing | |
| `IncorrectLookupParameters` exception | ❌ Missing | |

---

## SECTION 2: Staticfiles (`django.contrib.staticfiles`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BaseFinder` | ❌ Missing | |
| `class FileSystemFinder(dirs)` | ❌ Missing | |
| `class AppDirectoriesFinder` | ❌ Missing | |
| `class BaseStorageFinder` | ❌ Missing | |
| `class DefaultStorageFinder` | ❌ Missing | |
| `find(path, find_all)` | ❌ Missing | |
| `get_finders()` | ❌ Missing | |
| `get_finder(import_path)` | ❌ Missing | |
| `static()` template tag | ❌ Missing | |
| `staticfiles` storage | ❌ Missing | |
| `collectstatic` command | `collectstatic` | ⚠️ Partial | CLI exists but minimal |
| `staticfiles` views | ❌ Missing | Development serving |
| `static()` url pattern helper | ❌ Missing | |

---

## SECTION 3: Sites (`django.contrib.sites`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class SiteManager` | ❌ Missing | |
| `class Site` model (domain, name) | ❌ Missing | |
| `class RequestSite` | ❌ Missing | |
| `class CurrentSiteManager` | ❌ Missing | |
| `get_current_site(request)` | ❌ Missing | |
| `shortcut()` function | ❌ Missing | |
| `SiteMiddleware` | ❌ Missing | |

---

## SECTION 4: Sitemaps (`django.contrib.sitemaps`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Sitemap` | ❌ Missing | Entire sitemaps framework |
| `Sitemap.items()` | ❌ Missing | |
| `Sitemap.location(item)` | ❌ Missing | |
| `Sitemap.lastmod(item)` | ❌ Missing | |
| `Sitemap.changefreq` | ❌ Missing | |
| `Sitemap.priority` | ❌ Missing | |
| `sitemap` view | ❌ Missing | |
| `index` view | ❌ Missing | |
| `GenericSitemap` | ❌ Missing | |
| `FlatPageSitemap` | ❌ Missing | |

---

## SECTION 5: Flatpages (`django.contrib.flatpages`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class FlatPage` model | ❌ Missing | |
| `FlatPage.url, title, content, enable_comments` | ❌ Missing | |
| `FlatPage.registration_required` | ❌ Missing | |
| `FlatPage.sites` | ❌ Missing | |
| `flatpage` view | ❌ Missing | |
| `FlatpageFallbackMiddleware` | ❌ Missing | |

---

## SECTION 6: Redirects (`django.contrib.redirects`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Redirect` model | ❌ Missing | |
| `Redirect.site, old_path, new_path` | ❌ Missing | |
| `RedirectFallbackMiddleware` | ❌ Missing | |

---

## SECTION 7: Humanize (`django.contrib.humanize`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `apnumber(value)` | ❌ Missing | |
| `intcomma(value)` | ❌ Missing | Formats with commas |
| `intword(value)` | ❌ Missing | 1.0 million |
| `naturalday(value)` | ❌ Missing | "today", "yesterday" |
| `naturaltime(value)` | ❌ Missing | "3 minutes ago" |
| `ordinal(value)` | ❌ Missing | "1st", "2nd", "3rd" |

---

## SECTION 8: Content Types (`django.contrib.contenttypes`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class ContentType` model | ❌ Missing | |
| `ContentType.app_label` | ❌ Missing | |
| `ContentType.model` | ❌ Missing | |
| `ContentType.get_object_for_this_type(**kwargs)` | ❌ Missing | |
| `class GenericForeignKey` | ❌ Missing | |
| `GenericForeignKey.ct_field` | ❌ Missing | |
| `GenericForeignKey.fk_field` | ❌ Missing | |
| `class GenericRelation` | ❌ Missing | Reverse generic relation |
| `class GenericRel` | ❌ Missing | |
| `class ContentTypeManager` | ❌ Missing | |
| `get_content_type_cache()` | ❌ Missing | |

---

## SECTION 9: Syndication / Feeds (`django.contrib.syndication`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Feed` | ❌ Missing | Entire feed framework |
| `Feed.get_object(request, *args)` | ❌ Missing | |
| `Feed.items(obj)` | ❌ Missing | |
| `Feed.item_title(item)` | ❌ Missing | |
| `Feed.item_description(item)` | ❌ Missing | |
| `Feed.item_link(item)` | ❌ Missing | |
| `Feed.feed_extra_kwargs(obj)` | ❌ Missing | |
| `Feed.item_extra_kwargs(item)` | ❌ Missing | |
| RSS/Atom feed views | ❌ Missing | |

---

## SECTION 10: Messages (`django.contrib.messages`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Message` | `Message` | ✅ | Present |
| `add_message(request, level, message, extra_tags)` | `add_message()` | ✅ | |
| `get_messages(request)` | ❌ Missing | |
| `get_level(request)` | ❌ Missing | |
| `set_level(request, level)` | ❌ Missing | |
| `debug(request, message)` | ❌ Missing | |
| `info(request, message)` | ❌ Missing | |
| `success(request, message)` | ❌ Missing | |
| `warning(request, message)` | ❌ Missing | |
| `error(request, message)` | ❌ Missing | |
| `class BaseStorage` | ❌ Missing | |
| `class SessionStorage(BaseStorage)` | ❌ Missing | |
| `class CookieStorage(BaseStorage)` | ❌ Missing | |
| `class FallbackStorage(BaseStorage)` | ❌ Missing | |
| `class MessageMiddleware` | `MessageMiddleware` | ✅ | |
| `CONTEXT_PROCESSORS` | ❌ Missing | |

---

## SECTION 11: Sessions (`django.contrib.sessions`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class SessionBase` | `SessionStore` | ⚠️ Partial | |
| `SessionBase.get(key, default)` | ❌ Missing | |
| `SessionBase.__setitem__` | ❌ Missing | |
| `SessionBase.__getitem__` | ❌ Missing | |
| `SessionBase.pop(key)` | ❌ Missing | |
| `SessionBase.keys()` | ❌ Missing | |
| `SessionBase.values()` | ❌ Missing | |
| `SessionBase.set_expiry(value)` | ❌ Missing | |
| `SessionBase.get_expiry_age()` | ❌ Missing | |
| `SessionBase.get_expiry_date()` | ❌ Missing | |
| `SessionBase.get_expire_at_browser_close()` | ❌ Missing | |
| `SessionBase.create()` | ❌ Missing | |
| `SessionBase.save()` | ❌ Missing | |
| `SessionBase.delete()` | ❌ Missing | |
| `SessionBase.flush()` | ❌ Missing | |
| `SessionBase.cycle_key()` | ❌ Missing | |
| `class SessionStore (DB)` | ❌ Missing | |
| `class SessionStore (Cache)` | ❌ Missing | |
| `class SessionStore (File)` | ❌ Missing | |
| `class SessionStore (Signed cookies)` | ❌ Missing | |
| `class SessionMiddleware` | `SessionMiddleware` | ⚠️ Partial | |
| `CreateError` exception | ❌ Missing | |
| `UpdateError` exception | ❌ Missing | |

---

## SECTION 12: Postgres (`django.contrib.postgres`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| **Fields** | | | |
| `ArrayField(base_field)` | ❌ Missing | |
| `HStoreField` | ❌ Missing | |
| `JSONField` | ❌ Missing | |
| `RangeField` | ❌ Missing | |
| `IntegerRangeField` | ❌ Missing | |
| `DateRangeField` | ❌ Missing | |
| `DateTimeRangeField` | ❌ Missing | |
| `DecimalRangeField` | ❌ Missing | |
| `CICharField` (case insensitive) | ❌ Missing | |
| `CIEmailField` | ❌ Missing | |
| `CITextField` | ❌ Missing | |
| **Indexes** | | | |
| `BloomIndex` | ❌ Missing | |
| `BrinIndex` | ❌ Missing | |
| `BTreeIndex` | ❌ Missing | |
| `GinIndex` | ❌ Missing | |
| `GistIndex` | ❌ Missing | |
| `HashIndex` | ❌ Missing | |
| `SpGistIndex` | ❌ Missing | |
| **Aggregates** | | | |
| `ArrayAgg` | ❌ Missing | |
| `BitAnd` | ❌ Missing | |
| `BitOr` | ❌ Missing | |
| `BoolAnd` | ❌ Missing | |
| `BoolOr` | ❌ Missing | |
| `JSONBAgg` | ❌ Missing | |
| `StringAgg` | ❌ Missing | |
| `Corr` | ❌ Missing | |
| `CovarPop` | ❌ Missing | |
| `RegrAvgX` | ❌ Missing | |
| `RegrAvgY` | ❌ Missing | |
| `RegrCount` | ❌ Missing | |
| `RegrIntercept` | ❌ Missing | |
| `RegrR2` | ❌ Missing | |
| `RegrSlope` | ❌ Missing | |
| `RegrSXX` | ❌ Missing | |
| `RegrSXY` | ❌ Missing | |
| `RegrSYY` | ❌ Missing | |
| `Statistics` | ❌ Missing | |
| | **Entire postgres contrib module missing** | ❌ | |

---

## SECTION 13: GIS (`django.contrib.gis`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `gdal` | ❌ Missing | Entire GIS module missing |
| `geoip2` | ❌ Missing | |
| `geos` | ❌ Missing | |
| `measure` | ❌ Missing | |
| `proj` | ❌ Missing | |
| `raster` | ❌ Missing | |
| `serializers` | ❌ Missing | |
| `sitemaps` | ❌ Missing | |
| `admin` | ❌ Missing | |
| `forms` | ❌ Missing | |
| `widgets` | ❌ Missing | |
| `feeds` | ❌ Missing | |
| `GeoIP2` | ❌ Missing | |
| **Entire GIS contrib missing** | ❌ | Low-priority for Rust port |

---

## SECTION 14: Admin Docs (`django.contrib.admindocs`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `admindocs` module | ❌ Missing | |
| View/Model/Template documentation | ❌ Missing | |
| **Entire admindocs missing** | ❌ | |

---

## SECTION 15: i18n / Translation Utilities

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| **django.utils.translation** | | | |
| `gettext(message)` | `gettext()` | ✅ | |
| `ngettext(singular, plural, n)` | ❌ Missing | |
| `pgettext(context, message)` | ❌ Missing | |
| `npgettext(context, singular, plural, n)` | ❌ Missing | |
| `gettext_lazy(message)` | ❌ Missing | |
| `ngettext_lazy(singular, plural)` | ❌ Missing | |
| `pgettext_lazy(context, message)` | ❌ Missing | |
| `activate(language)` | ❌ Missing | |
| `deactivate()` | ❌ Missing | |
| `get_language()` | ❌ Missing | |
| `get_language_bidi()` | ❌ Missing | |
| `get_language_from_request(request)` | ❌ Missing | |
| `override(language)` (context manager) | ❌ Missing | |
| `class to_language(locale)` | ❌ Missing | |
| `class to_locale(language)` | ❌ Missing | |
| `class templatize(src)` | ❌ Missing | |
| `trans_real` (real impl) | ❌ Missing | |
| `trans_null` (no-op impl) | ❌ Missing | |
| Locale middleware | ❌ Missing | |
| `{% trans %}` template tag | ❌ Missing | |
| `{% blocktrans %}` template tag | ❌ Missing | |
| Locale path resolution | ❌ Missing | |
| `.mo` / `.po` file loading | ❌ Missing | |

---

## Summary

### Admin: Basic structure only
- ✅ AdminSite with register/index/app_index
- ✅ ModelAdmin with basic CRUD views (changelist, add, change, delete)
- ✅ Basic list_display
- ❌ Missing: Admin actions (delete_selected)
- ❌ Missing: InlineModelAdmin (StackedInline, TabularInline)
- ❌ Missing: Filters, autocomplete, raw_id_fields
- ❌ Missing: search_fields, list_filter, date_hierarchy
- ❌ Missing: Admin decorators (@register, @display, @action)
- ❌ Missing: Permission checks
- ❌ Missing: Admin forms
- ❌ Missing: History view
- ❌ Missing: auto-generated admin templates

### Staticfiles: CLI only
- ✅ `collectstatic` command
- ❌ Missing: Finders (FileSystem, AppDirectories)
- ❌ Missing: Storage backend
- ❌ Missing: `{% static %}` template tag
- ❌ Missing: Development serving view

### All Other Contrib: ❌ Entirely Missing
- ❌ Sites framework
- ❌ Sitemaps framework
- ❌ Flatpages
- ❌ Redirects
- ❌ Humanize template tags
- ❌ ContentTypes framework
- ❌ Syndication/Feeds (RSS/Atom)
- ❌ Postgres-specific fields, indexes, aggregates, functions, search
- ❌ GIS entire module
- ❌ Admin Docs
- ❌ Messages: retrieval and convenience functions missing
- ❌ Sessions: full API and backends missing
- ❌ i18n: only basic gettext

### Rjango has implemented app-level contrib
- ✅ Messages: basic add_message, Message struct
- ✅ Sessions: basic session middleware
- ✅ Admin: basic site + model admin
- ✅ Staticfiles: CLI command
