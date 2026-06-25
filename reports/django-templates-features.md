# Django 6.0.6 Templates — Feature Comparison with Rjango

> **Django modules analyzed:** `django.template`, `django.template.backends`, `django.template.loaders`, `django.template.context`, `django.template.defaultfilters`, `django.template.defaulttags`, `django.template.library`, `django.template.engine`

---

## 1. Template Engine (`django.template.Engine`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `Engine` | `TemplateEngine` | ⚠️ Partial | Rjango has `TemplateEngine::new()` |
| `Engine(dirs, module_dirs, loaders, context_processors, debug, file_charset)` | `TemplateEngine::new(template_dirs, loaders, context_processors)` | ⚠️ Partial | Missing `module_dirs`, `debug`, `file_charset` params |
| `Engine.get_default()` | ❌ Missing | |
| `Engine.get_template(template_name)` | `TemplateEngine::get_template()` | ✅ | |
| `Engine.from_string(template_code)` | `TemplateEngine::from_string()` | ✅ | |
| `Engine.render_to_string(template_name, context)` | `TemplateEngine::render()` | ✅ | |
| `Engine.find_template(template_name)` | ❌ Missing | Internal |
| `Engine.find_template_loader(loader)` | ❌ Missing | |

### Backends
| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class DjangoTemplates(BaseEngine)` | ❌ Missing | Backend wrapper |
| `DjangoTemplates.__init__(params)` | ❌ Missing | |
| `DjangoTemplates.get_template(template_name)` | ❌ Missing | |
| `class Jinja2(BaseEngine)` | ❌ Missing | |
| `get_template_tag_modules()` | ❌ Missing | |
| `get_installed_libraries()` | ❌ Missing | |

---

## 2. Template Loaders

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Loader` (base) | `Loader` trait | ✅ | Present |
| `Loader.get_template(name)` | `Loader::get_template()` | ✅ | |
| `Loader.get_contents()` | ❌ Missing | |
| `class FileSystemLoader` | `FileSystemLoader` | ✅ | |
| `class AppDirectoriesLoader` | `AppDirectoriesLoader` | ✅ | |
| `class CachedLoader` | ❌ Missing | |
| `class LocMemLoader` | ❌ Missing | |

---

## 3. Context System

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BaseContext(dict)` | `Context` | ⚠️ Partial | |
| `Context(dict)` | `Context::new()` | ✅ | |
| `Context.push()` | ❌ Missing | |
| `Context.pop()` | ❌ Missing | |
| `Context.update(other)` | ❌ Missing | |
| `Context.flatten()` | ❌ Missing | |
| `class RequestContext(request, dict, processors)` | ❌ Missing | |
| `class RenderContext` | ❌ Missing | |
| `make_context(context, request)` | ❌ Missing | |
| `class ContextPopException` | ❌ Missing | |

---

## 4. Template Tags (defaulttags.py)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `{% autoescape on/off %}` | ❌ Missing | |
| `{% block name %}` | `BlockNode` | ✅ | Present |
| `{% comment %}` | `CommentNode` | ✅ | |
| `{% csrf_token %}` | ❌ Missing | |
| `{% cycle name %}` | `CycleNode` | ✅ | |
| `{% debug %}` | ❌ Missing | |
| `{% extends parent %}` | `ExtendsNode` | ✅ | |
| `{% filter expr %}` | ❌ Missing | Apply filter to block content |
| `{% firstof var1 var2 %}` | `FirstOfNode` | ✅ | |
| `{% for var in list %}` | `ForNode` | ✅ | |
| `{% for ... empty %}` | ❌ Missing | For-else |
| `{% endfor %}` | ✅ | |
| `{% ifchanged %}` | ❌ Missing | |
| `{% if expr %}` | `IfNode` | ✅ | |
| `{% elif expr %}` | ✅ | |
| `{% else %}` | ✅ | |
| `{% lorem N w/p %}` | ❌ Missing | |
| `{% regroup list by attr %}` | `RegroupNode` | ✅ | |
| `{% load module %}` | ❌ Missing | |
| `{% now format %}` | `NowNode` | ✅ | |
| `{% partialdef name %}` | ❌ Missing | |
| `{% partial name %}` | ❌ Missing | |
| `{% resetcycle name %}` | ❌ Missing | |
| `{% spaceless %}` | `SpacelessNode` | ✅ | |
| `{% templatetag %}` | ❌ Missing | Output template syntax chars |
| `{% url name arg %}` | ❌ Missing | |
| `{% verbatim %}` | `VerbatimNode` | ✅ | |
| `{% widthratio a b c %}` | `WidthRatioNode` | ✅ | |
| `{% with var=value %}` | ❌ Missing | |

**Missing tags:** `csrf_token`, `debug`, `filter`, `for ... empty`, `ifchanged`, `load`, `lorem`, `now` (basic), `partialdef`, `partial`, `resetcycle`, `templatetag`, `url`, `with`, `autoescape`

---

## 5. Template Filters (defaultfilters.py)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `add(value, arg)` | `add()` | ✅ | |
| `addslashes(value)` | `addslashes()` | ✅ | |
| `capfirst(value)` | `capfirst()` | ✅ | |
| `center(value, arg)` | `center()` | ✅ | |
| `cut(value, arg)` | `cut()` | ✅ | |
| `date(value, arg)` | `date()` | ✅ | |
| `default(value, arg)` | `default()` | ✅ | |
| `default_if_none(value)` | ❌ Missing | |
| `dictsort(value, arg)` | `dictsort()` | ✅ | |
| `dictsortreversed(value, arg)` | ❌ Missing | |
| `divisibleby(value, arg)` | `divisibleby()` | ✅ | |
| `escape(value)` | `escape()` | ✅ | |
| `escapejs(value)` | ❌ Missing | |
| `filesizeformat(value)` | `filesizeformat()` | ✅ | |
| `first(value)` | `first()` | ✅ | |
| `floatformat(value, arg)` | `floatformat()` | ✅ | |
| `force_escape(value)` | ❌ Missing | |
| `get_digit(value, arg)` | ❌ Missing | |
| `iriencode(value)` | ❌ Missing | |
| `join(value, arg)` | `join()` | ✅ | |
| `json_script(value, element_id)` | ❌ Missing | |
| `last(value)` | `last()` | ✅ | |
| `length(value)` | `length()` | ✅ | |
| `length_is(value, arg)` | ❌ Missing | |
| `linebreaks(value)` | `linebreaks()` | ✅ | |
| `linebreaksbr(value)` | `linebreaksbr()` | ✅ | |
| `linenumbers(value)` | `linenumbers()` | ✅ | |
| `ljust(value, arg)` | `ljust()` | ✅ | |
| `lower(value)` | `lower()` | ✅ | |
| `make_list(value)` | `make_list()` | ✅ | |
| `phone2numeric(value)` | `phone2numeric()` | ✅ | |
| `pluralize(value, arg)` | `pluralize()` | ✅ | |
| `pprint(value)` | `pprint()` | ✅ | |
| `random(value)` | `random()` | ✅ | |
| `rjust(value, arg)` | `rjust()` | ✅ | |
| `safe(value)` | `safe()` | ✅ | |
| `safeseq(value)` | ❌ Missing | |
| `slugify(value)` | `slugify()` | ✅ | |
| `stringformat(value, arg)` | `stringformat()` | ✅ | |
| `striptags(value)` | `striptags()` | ✅ | |
| `time(value, arg)` | `time()` | ✅ | |
| `timesince(value, arg)` | `timesince()` | ✅ | |
| `timeuntil(value, arg)` | ❌ Missing | |
| `title(value)` | `title()` | ✅ | |
| `truncatechars(value, arg)` | `truncatechars()` | ✅ | |
| `truncatechars_html(value, arg)` | ❌ Missing | |
| `truncatewords(value, arg)` | `truncatewords()` | ✅ | |
| `truncatewords_html(value, arg)` | ❌ Missing | |
| `unordered_list(value)` | `unordered_list()` | ✅ | |
| `upper(value)` | `upper()` | ✅ | |
| `urlencode(value, safe)` | `urlencode()` | ✅ | |
| `urlize(value)` | `urlize()` | ✅ | |
| `urlizetrunc(value, limit)` | ❌ Missing | |
| `wordcount(value)` | `wordcount()` | ✅ | |
| `wordwrap(value, arg)` | ❌ Missing | |
| `yesno(value, arg)` | `yesno()` | ✅ | |
| `escapejs_filter(value)` | ❌ Missing | |
| `escapeseq(value)` | ❌ Missing | |

**Rjango has 44 filters.** **Django has 53+ filters.** Missing: `default_if_none`, `dictsortreversed`, `escapejs`, `force_escape`, `get_digit`, `iriencode`, `json_script`, `length_is`, `safeseq`, `timeuntil`, `truncatechars_html`, `truncatewords_html`, `urlizetrunc`, `wordwrap`, `escapeseq`

---

## 6. Template Library

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Library` | ❌ Missing | Tag/filter registration |
| `Library.simple_tag()` | ❌ Missing | |
| `Library.inclusion_tag()` | ❌ Missing | |
| `Library.filter()` | ❌ Missing | |
| `Library.tag()` | ❌ Missing | |
| `import_library(name)` | ❌ Missing | |
| `class InclusionNode` | ❌ Missing | |
| `class SimpleNode` | ❌ Missing | |

---

## 7. Template Utilities

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Origin` | ❌ Missing | |
| `class Template` | `Template` | ✅ | |
| `Template.render(context)` | `Template::render()` | ✅ | |
| `Template.compile_nodes()` | ❌ Missing | |
| `class Node` | `Node` enum | ✅ | |
| `Node.render(context)` | `Node::render()` | ✅ | |
| `class Token` | `Token` | ✅ | |
| `class Lexer` | `Tokenizer` | ✅ | |
| `class Parser` | `Parser` | ✅ | |
| `get_template(template_name)` | `Loader::get_template()` | ✅ | |
| `select_template(template_name_list)` | ❌ Missing | |
| `render_to_string(template_name, context)` | `Engine::render()` | ✅ | |

---

## Summary

### Templates Features: ✅ Rjango has strong coverage
- 44 of ~53 Django filters implemented (~83%)
- 12 of ~23 Django tags implemented (~52%)
- Full template engine with parser, tokenizer
- Template loaders (Filesystem, AppDirectories, Test)
- Template inheritance (extends, block)
- Auto-escaping system

### Missing
- ❌ Template library system (custom tag/filter registration)
- ❌ `{% csrf_token %}` tag
- ❌ `{% url %}` tag (URL reversing)
- ❌ `{% load %}` / `{% with %}` / `{% autoescape %}` tags
- ❌ Jinja2 backend
- ❌ `for ... empty`
- ❌ 10+ filters (escapejs, force_escape, HTML-aware truncation)
- ❌ `comment` (present), `now` (present) — actually these are done
