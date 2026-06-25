# Django 6.0.6 URLs, Views, Test, CLI, Migrations — Feature Comparison with Rjango

> **Django modules analyzed:** `django.urls`, `django.views`, `django.test`, `django.core.management`, `django.db.migrations`, `django.dispatch`

---

## SECTION 1: URL Dispatcher (`django.urls`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `resolve(path, urlconf)` | `resolve()` | ✅ | Present |
| `reverse(viewname, args, kwargs)` | `reverse()` | ✅ | |
| `reverse_lazy(viewname, args, kwargs)` | ❌ Missing | Lazy version |
| `clear_url_caches()` | ❌ Missing | |
| `set_script_prefix(prefix)` | ❌ Missing | |
| `get_script_prefix()` | ❌ Missing | |
| `set_urlconf(urlconf)` | ❌ Missing | |
| `get_urlconf(default)` | ❌ Missing | |
| `is_valid_path(path, urlconf)` | ❌ Missing | |
| `translate_url(url, lang_code)` | ❌ Missing | |
| `path(route, view, kwargs, name)` | `path()` / `route()` | ✅ | |
| `re_path(route, view, kwargs, name)` | ❌ Missing | Regex paths |
| `include(arg, namespace)` | `include()` | ✅ | |
| `register_converter(converter, type_name)` | `register_converter()` | ✅ | |

### Converters

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class IntConverter` | `IntConverter` | ✅ | |
| `class StringConverter` | `StringConverter` | ✅ | |
| `class UUIDConverter` | `UUIDConverter` | ✅ | |
| `class SlugConverter` | `SlugConverter` | ✅ | |
| `class PathConverter` | `PathConverter` | ✅ | |
| `get_converters()` | ❌ Missing | |

### URL Resolvers

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class URLPattern(pattern, callback, name)` | `URLPattern` | ✅ | |
| `class URLResolver(pattern, callback, namespace)` | `URLResolver` | ✅ | |
| `class ResolverMatch(func, args, kwargs, url_name, ...)` | `ResolverMatch` | ✅ | |
| `class RoutePattern(route)` | `RoutePattern` | ✅ | |
| `class RegexPattern(route)` | ❌ Missing | |
| `class LocalePrefixPattern` | ❌ Missing | |
| `get_resolver(urlconf)` | ❌ Missing | |
| `class CheckURLMixin` | ❌ Missing | |

---

## SECTION 2: Generic Views (`django.views`)

### 2a. Base views

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class View` | `View` trait | ✅ | |
| `View.as_view()` | ❌ Missing | Class-based view entry point |
| `View.dispatch(request, *args, **kwargs)` | ❌ Missing | |
| `View.http_method_not_allowed(request)` | ❌ Missing | |
| `View.options(request)` | ❌ Missing | |
| `View.setup(request, *args, **kwargs)` | ❌ Missing | |
| `class TemplateView` | `TemplateView` | ✅ | |
| `TemplateView.template_name` | ✅ | |
| `TemplateView.get_context_data()` | ✅ | |
| `class RedirectView` | ❌ Missing | |
| `RedirectView.get_redirect_url()` | ❌ Missing | |

### 2b. List views

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class MultipleObjectMixin` | ❌ Missing | |
| `MultipleObjectMixin.model` | ❌ Missing | |
| `MultipleObjectMixin.queryset` | ❌ Missing | |
| `MultipleObjectMixin.context_object_name` | ❌ Missing | |
| `MultipleObjectMixin.paginate_by` | ❌ Missing | |
| `MultipleObjectMixin.page_kwarg` | ❌ Missing | |
| `MultipleObjectMixin.get_queryset()` | ❌ Missing | |
| `MultipleObjectMixin.paginate_queryset()` | ❌ Missing | |
| `class BaseListView` | ❌ Missing | |
| `class MultipleObjectTemplateResponseMixin` | ❌ Missing | |
| `class ListView` | `ListView` | ⚠️ Partial | Rjango has basic struct |

### 2c. Detail views

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class SingleObjectMixin` | ❌ Missing | |
| `SingleObjectMixin.get_object()` | ❌ Missing | |
| `SingleObjectMixin.get_queryset()` | ❌ Missing | |
| `class BaseDetailView` | ❌ Missing | |
| `class SingleObjectTemplateResponseMixin` | ❌ Missing | |
| `class DetailView` | `DetailView` | ⚠️ Partial | Rjango has basic struct |

### 2d. Form/Edit views

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class FormMixin` | ❌ Missing | |
| `FormMixin.form_class` | ❌ Missing | |
| `FormMixin.success_url` | ❌ Missing | |
| `FormMixin.get_form()` | ❌ Missing | |
| `FormMixin.form_valid(form)` | ❌ Missing | |
| `FormMixin.form_invalid(form)` | ❌ Missing | |
| `class ModelFormMixin` | ❌ Missing | |
| `class ProcessFormView` | ❌ Missing | |
| `class BaseFormView` | ❌ Missing | |
| `class FormView` | `FormView` | ⚠️ Partial | Rjango basic struct |
| `class CreateView` | `CreateView` | ⚠️ Partial | |
| `class UpdateView` | `UpdateView` | ⚠️ Partial | |
| `class DeleteView` | `DeleteView` | ⚠️ Partial | |
| `class DeletionMixin` | ❌ Missing | |

### 2e. Date-based views

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class YearMixin` | ❌ Missing | |
| `class MonthMixin` | ❌ Missing | |
| `class DayMixin` | ❌ Missing | |
| `class WeekMixin` | ❌ Missing | |
| `class DateMixin` | ❌ Missing | |
| `class BaseDateListView` | ❌ Missing | |
| `class ArchiveIndexView` | ❌ Missing | |
| `class YearArchiveView` | ❌ Missing | |
| `class MonthArchiveView` | ❌ Missing | |
| `class WeekArchiveView` | ❌ Missing | |
| `class DayArchiveView` | ❌ Missing | |
| `class TodayArchiveView` | ❌ Missing | |
| `class DateDetailView` | ❌ Missing | |

### 2f. View decorators

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `require_http_methods(methods)` | `require_http_methods()` | ✅ | |
| `require_POST()` | `require_post()` | ✅ | |
| `require_GET()` | `require_get()` | ✅ | |
| `require_safe()` | ❌ Missing | GET + HEAD only |

---

## SECTION 3: Test Utilities (`django.test`)

### 3a. Test Client

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Client` | `TestClient` | ⚠️ Partial | |
| `Client.get(path, data, follow, secure)` | `TestClient::get()` | ✅ | |
| `Client.post(path, data, content_type, follow)` | `TestClient::post()` | ✅ | |
| `Client.head(path, data, follow)` | ❌ Missing | |
| `Client.options(path, data, follow)` | ❌ Missing | |
| `Client.put(path, data, content_type, follow)` | ❌ Missing | |
| `Client.patch(path, data, content_type, follow)` | ❌ Missing | |
| `Client.delete(path, data, content_type, follow)` | ❌ Missing | |
| `Client.trace(path, data, follow)` | ❌ Missing | |
| `Client.login(username, password)` | ❌ Missing | |
| `Client.logout()` | ❌ Missing | |
| `Client.force_login(user, backend)` | ❌ Missing | |
| `Client.cookies` | ❌ Missing | |
| `Client.session` | ❌ Missing | |
| `Client.handler` | ❌ Missing | |
| `class RequestFactory` | ❌ Missing | |
| `RequestFactory.get(path)` | ❌ Missing | |
| `RequestFactory.post(path)` | ❌ Missing | |
| `class AsyncClient` | ❌ Missing | |
| `class AsyncRequestFactory` | ❌ Missing | |

### 3b. Test Cases

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class SimpleTestCase` | `RjangoTestCase` | ⚠️ Partial | |
| `SimpleTestCase.assertContains(response, text)` | ❌ Missing | |
| `SimpleTestCase.assertNotContains(response, text)` | ❌ Missing | |
| `SimpleTestCase.assertTemplateUsed(response, name)` | ❌ Missing | |
| `SimpleTestCase.assertTemplateNotUsed(response, name)` | ❌ Missing | |
| `SimpleTestCase.assertRedirects(response, url)` | ❌ Missing | |
| `SimpleTestCase.assertHTMLEqual(html1, html2)` | ❌ Missing | |
| `SimpleTestCase.assertInHTML(needle, haystack)` | ❌ Missing | |
| `SimpleTestCase.assertJSONEqual(raw, expected)` | ❌ Missing | |
| `SimpleTestCase.assertJSONNotEqual(raw, expected)` | ❌ Missing | |
| `class TransactionTestCase(SimpleTestCase)` | ❌ Missing | Database transactions |
| `class TestCase(TransactionTestCase)` | ❌ Missing | DB + fixtures |
| `TestCase.fixtures` | ❌ Missing | |
| `class LiveServerTestCase` | ❌ Missing | |
| `class SeleniumTestCase` | ❌ Missing | |
| `skipIfDBFeature(*features)` | ❌ Missing | |
| `skipUnlessDBFeature(*features)` | ❌ Missing | |
| `skipUnlessAnyDBFeature(*features)` | ❌ Missing | |
| `class TestData` | ❌ Missing | |

### 3c. Test Runner

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class DiscoverRunner` | `TestRunner` | ⚠️ Partial | |
| `DiscoverRunner.run_tests(test_labels)` | `TestRunner::run()` | ✅ | |
| `DiscoverRunner.setup_test_environment()` | ❌ Missing | |
| `DiscoverRunner.teardown_test_environment()` | ❌ Missing | |
| `DiscoverRunner.setup_databases()` | ❌ Missing | |
| `DiscoverRunner.teardown_databases()` | ❌ Missing | |
| `DiscoverRunner.build_suite(test_labels)` | ❌ Missing | |
| `DiscoverRunner.run_suite(suite)` | ❌ Missing | |
| `DiscoverRunner.get_resultclass()` | ❌ Missing | |
| `class ParallelTestSuite` | ❌ Missing | |
| `class RemoteTestRunner` | ❌ Missing | |
| `class Shuffler` | ❌ Missing | |
| `class DebugSQLTextTestResult` | ❌ Missing | |
| `class PDBDebugResult` | ❌ Missing | |
| `shuffle_tests(tests, shuffler)` | ❌ Missing | |
| `reorder_test_bin(tests)` | ❌ Missing | |
| `get_max_test_processes()` | ❌ Missing | |

---

## SECTION 4: Management Commands (`django.core.management`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `runserver` | `runserver` | ✅ | |
| `startproject` | `startproject` | ✅ | |
| `startapp` | `startapp` | ✅ | |
| `migrate` | `migrate` | ✅ | |
| `makemigrations` | `makemigrations` | ✅ | |
| `dbshell` | `dbshell` | ✅ | |
| `createsuperuser` | `createsuperuser` | ✅ | |
| `collectstatic` | `collectstatic` | ✅ | |
| `test` | `test` | ✅ | |
| `check` | `check` | ✅ | |
| `validate` | `validate` | ✅ | |
| `showmigrations` | `showmigrations` | ✅ | |
| `shell` | `shell` | ✅ | |
| `sqlmigrate` | ❌ Missing | |
| `sqlflush` | ❌ Missing | |
| `sqlsequencereset` | ❌ Missing | |
| `dumpdata` | ❌ Missing | Serialize DB to JSON |
| `loaddata` | ❌ Missing | Load fixtures from files |
| `inspectdb` | ❌ Missing | Reverse-engineer DB tables |
| `flush` | ❌ Missing | Clear DB data |
| `testserver` | ❌ Missing | |
| `sendtestemail` | ❌ Missing | |
| `makemessages` | ❌ Missing | |
| `compilemessages` | ❌ Missing | |
| `createcachetable` | ❌ Missing | |
| `diffsettings` | ❌ Missing | |
| `optimizemigration` | ❌ Missing | |
| `squashmigrations` | ❌ Missing | |

---

## SECTION 5: Migrations (`django.db.migrations`)

### 5a. Operations

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class CreateModel(name, fields, options)` | `CreateModel` | ✅ | |
| `class DeleteModel(name)` | `DeleteModel` | ✅ | |
| `class RenameModel(old_name, new_name)` | ❌ Missing | |
| `class AlterModelTable(name, table)` | ❌ Missing | |
| `class AlterModelTableComment(name, comment)` | ❌ Missing | |
| `class AlterModelOptions(name, options)` | ❌ Missing | |
| `class AlterModelManagers(name, managers)` | ❌ Missing | |
| `class AlterTogetherOptionOperation` | ❌ Missing | |
| `class AlterUniqueTogether(name, unique_together)` | ❌ Missing | |
| `class AlterIndexTogether(name, index_together)` | ❌ Missing | |
| `class AlterOrderWithRespectTo(name, order)` | ❌ Missing | |
| `class AddField(model, name, field)` | `AddField` | ✅ | |
| `class RemoveField(model, name)` | `RemoveField` | ✅ | |
| `class AlterField(model, name, field)` | `AlterField` | ✅ | |
| `class RenameField(model, old_name, new_name)` | `RenameField` | ✅ | |
| `class AddIndex(model, index)` | ❌ Missing | |
| `class RemoveIndex(model, name)` | ❌ Missing | |
| `class RenameIndex(model, old_name, new_name)` | ❌ Missing | |
| `class AddConstraint(model, constraint)` | ❌ Missing | |
| `class RemoveConstraint(model, name)` | ❌ Missing | |
| `class AlterConstraint(model, name, constraint)` | ❌ Missing | |
| `class SeparateDatabaseAndState(database, state)` | ❌ Missing | |
| `class RunSQL(sql, reverse_sql)` | ❌ Missing | |
| `class RunPython(code, reverse_code)` | ❌ Missing | |

### 5b. Migration Framework

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Migration(name, app_label)` | ❌ Missing | |
| `Migration.operations` | ❌ Missing | |
| `Migration.dependencies` | ❌ Missing | |
| `Migration.replace` | ❌ Missing | |
| `class Autodetector` | `MigrationDetector` | ⚠️ Partial | |
| `Autodetector.changes(graph, trim_to_apps)` | ❌ Missing | |
| `class MigrationExecutor` | ❌ Missing | Run migrations |
| `class MigrationLoader` | ❌ Missing | Load from files |
| `class MigrationRecorder` | ❌ Missing | DB recording |
| `class MigrationQuestioner` | ❌ Missing | Interactive questions |
| `class MigrationWriter` | ❌ Missing | File generation |
| `class MigrationOptimizer` | ❌ Missing | |
| `class State` | ❌ Missing | Project state tracking |
| `class ProjectState` | ❌ Missing | |
| `class AppState` | ❌ Missing | |

---

## SECTION 6: Signals & Dispatch

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Signal` | `Signal` | ✅ | |
| `Signal.connect(receiver, sender, weak, dispatch_uid)` | `Signal::connect()` | ✅ | |
| `Signal.disconnect(receiver, sender, dispatch_uid)` | `Signal::disconnect()` | ✅ | |
| `Signal.send(sender, **kwargs)` | `Signal::send()` | ✅ | |
| `Signal.send_robust(sender, **kwargs)` | ❌ Missing | Doesn't abort on exceptions |
| `receiver(signal, **kwargs)` decorator | ❌ Missing | |

### Model signals (not yet implemented by current ORM)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `pre_init` | ❌ Missing | |
| `post_init` | ❌ Missing | |
| `pre_save` | ❌ Missing | |
| `post_save` | ❌ Missing | |
| `pre_delete` | ❌ Missing | |
| `post_delete` | ❌ Missing | |
| `m2m_changed` | ❌ Missing | |

---

## Summary

### URLs: Strong parity ✅
- ALL converters implemented (int, str, slug, uuid, path)
- URL resolution and reversal
- `include()` for modular configs
- URLPattern / URLResolver
- ❌ Missing: `re_path()` for regex routes
- ❌ Missing: `reverse_lazy()`, `LocalePrefixPattern`
- ❌ Missing: Script prefix, URL cache clearing

### Views: Basic structure, missing integration
- ✅ TemplateView, ListView, DetailView, FormView, CreateView, UpdateView, DeleteView (basic structs)
- ❌ Missing: Full class-based view lifecycle (dispatch, setup)
- ❌ Missing: Mixin integration (MultipleObjectMixin, SingleObjectMixin)
- ❌ Missing: Date-based archive views (entire system)
- ❌ Missing: RedirectView
- ❌ Missing: `as_view()` class method entry point

### Test: Basic client + runner, missing assertions
- ✅ TestClient with GET/POST
- ✅ TestRunner
- ✅ TestCase
- ❌ Missing: Full test assertions (assertContains, assertTemplateUsed, assertRedirects)
- ❌ Missing: RequestFactory
- ❌ Missing: AsyncClient/AsyncRequestFactory
- ❌ Missing: LiveServerTestCase
- ❌ Missing: Database test setup/teardown

### CLI: 13 commands present, 14+ missing
- ✅ 13 commands implemented
- ❌ Missing: dumpdata, loaddata, inspectdb, sqlmigrate, flush, makemessages, etc.

### Migrations: 6 operations present, 14+ missing
- ✅ CreateModel, DeleteModel, AddField, RemoveField, AlterField, RenameField
- ❌ Missing: AddIndex, RemoveIndex, RenameIndex, AddConstraint, RemoveConstraint, AlterConstraint
- ❌ Missing: Migration framework (Executor, Loader, Recorder, Writer, Questioner)
- ❌ Missing: RunSQL, RunPython
- ❌ Missing: State management
