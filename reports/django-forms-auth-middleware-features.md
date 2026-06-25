# Django 6.0.6 Forms, Auth & Middleware — Feature Comparison with Rjango

> **Django modules analyzed:** `django.forms`, `django.contrib.auth`, `django.contrib.sessions`, `django.contrib.messages`, `django.middleware`

---

## SECTION 1: Forms (`django.forms`)

### 1a. Form Fields

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Field` (base) | `Field` | ✅ | Present |
| `Field.required` | `Field::required` | ✅ | |
| `Field.label` | `Field::label` | ✅ | |
| `Field.initial` | `Field::initial` | ✅ | |
| `Field.widget` | `Field::widget` | ✅ | |
| `Field.help_text` | `Field::help_text` | ✅ | |
| `Field.error_messages` | ❌ Missing | |
| `Field.validators` | `Field::validators` | ✅ | |
| `Field.localize` | ❌ Missing | |
| `Field.disabled` | ❌ Missing | |
| `Field.label_suffix` | ❌ Missing | |
| `Field.widget_attrs` | ❌ Missing | |
| `Field.to_python(value)` | `Field::to_python()` | ✅ | |
| `Field.validate(value)` | `Field::validate()` | ✅ | |
| `Field.run_validators(value)` | `Field::run_validators()` | ✅ | |
| `Field.clean(value)` | `Field::clean()` | ✅ | |
| `Field.bound_data(data, initial)` | ❌ Missing | |
| `Field.prepare_value(value)` | ❌ Missing | |
| `Field.get_bound_field(form, field_name)` | ❌ Missing | |
| `class CharField(max_length, min_length, strip)` | `CharField` | ✅ | |
| `class IntegerField(min_value, max_value)` | `IntegerField` | ✅ | |
| `class FloatField(max_value, min_value)` | `FloatField` | ✅ | |
| `class DecimalField(max_digits, decimal_places)` | ❌ Missing | |
| `class BooleanField` | `BooleanField` | ✅ | |
| `class NullBooleanField` | ❌ Missing | |
| `class DateField(input_formats)` | ❌ Missing | |
| `class TimeField(input_formats)` | ❌ Missing | |
| `class DateTimeField(input_formats)` | ❌ Missing | |
| `class DurationField` | ❌ Missing | |
| `class ChoiceField(choices)` | `ChoiceField` | ✅ | |
| `class TypedChoiceField(choices, coerce)` | ❌ Missing | |
| `class MultipleChoiceField` | ❌ Missing | |
| `class TypedMultipleChoiceField` | ❌ Missing | |
| `class EmailField` | `EmailField` | ✅ | |
| `class URLField` | `URLField` | ✅ | |
| `class FileField` | ❌ Missing | |
| `class ImageField` | ❌ Missing | |
| `class RegexField(regex)` | ❌ Missing | |
| `class SlugField` | ❌ Missing | |
| `class UUIDField` | ❌ Missing | |
| `class IPAddressField` | ❌ Missing | |
| `class GenericIPAddressField` | ❌ Missing | |
| `class SplitDateTimeField` | ❌ Missing | |
| `class JSONField` | ❌ Missing | |
| `class FilePathField` | ❌ Missing | |
| `class HiddenInput` widget | `HiddenInput` | ✅ | |

### 1b. Form Widgets

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Widget(attrs)` | `Widget` | ✅ | Present |
| `Widget.render(name, value, attrs, renderer)` | ❌ Missing | |
| `Widget.value_from_datadict(data, files, name)` | ❌ Missing | |
| `Widget.get_context(name, value, attrs)` | ❌ Missing | |
| `Widget.format_value(value)` | ❌ Missing | |
| `Widget.id_for_label(id_)` | ❌ Missing | |
| `class Media` | ❌ Missing | CSS/JS media |
| `class Input` | ✅ | |
| `class TextInput` | `TextInput` | ✅ | |
| `class NumberInput` | `NumberInput` | ✅ | |
| `class EmailInput` | `EmailInput` | ✅ | |
| `class URLInput` | ❌ Missing | |
| `class PasswordInput` | `PasswordInput` | ✅ | |
| `class HiddenInput` | `HiddenInput` | ✅ | |
| `class MultipleHiddenInput` | ❌ Missing | |
| `class Textarea` | `Textarea` widget | ✅ | |
| `class DateInput` | `DateInput` | ✅ | |
| `class DateTimeInput` | `DateTimeInput` | ✅ | |
| `class TimeInput` | ❌ Missing | |
| `class Select(choices)` | `Select` | ✅ | |
| `class SelectMultiple` | ❌ Missing | |
| `class RadioSelect` | `RadioSelect` | ✅ | |
| `class CheckboxInput` | `CheckboxInput` | ✅ | |
| `class CheckboxSelectMultiple` | ❌ Missing | |
| `class FileInput` | `FileInput` | ✅ | |
| `class ClearableFileInput` | ❌ Missing | |
| `class ColorInput` | ❌ Missing | |
| `class SearchInput` | ❌ Missing | |
| `class TelInput` | ❌ Missing | |
| `class SplitDateTimeWidget` | ❌ Missing | |
| `class HiddenInput` | ✅ | |

### 1c. Form Classes

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Form` | `Form` | ✅ | Present |
| `Form.is_valid()` | `Form::is_valid()` | ✅ | |
| `Form.cleaned_data` | `Form::cleaned_data()` | ✅ | |
| `Form.errors` | `Form::errors()` | ✅ | |
| `Form.fields` | `Form::fields()` | ✅ | |
| `Form.initial` | ❌ Missing | |
| `Form.data` | ❌ Missing | |
| `Form.full_clean()` | ❌ Missing | |
| `Form.clean()` | ❌ Missing | |
| `Form.clean_FIELD()` | ❌ Missing | Per-field hooks |
| `Form.add_error(field, error)` | ❌ Missing | |
| `Form.has_error(field, code)` | ❌ Missing | |
| `Form.non_field_errors()` | ❌ Missing | |
| `Form.as_table()` | `Form::as_table()` | ✅ | |
| `Form.as_p()` | `Form::as_p()` | ✅ | |
| `Form.as_div()` | `Form::as_div()` | ✅ | |
| `Form.as_ul()` | ❌ Missing | |
| `Form.has_changed()` | ❌ Missing | |
| `Form.changed_data` | ❌ Missing | |
| `Form.errors.as_data()` | ❌ Missing | |
| `Form.errors.as_json()` | ❌ Missing | |
| `Form.errors.get_json_data()` | ❌ Missing | |

### 1d. Form Validation

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BaseValidator` | ❌ Missing | |
| `RegexValidator` | ✅ | |
| `EmailValidator` | ✅ | |
| `URLValidator` | ✅ | |
| `MinLengthValidator` | ✅ | |
| `MaxLengthValidator` | ✅ | |
| `MinValueValidator` | ❌ Missing | |
| `MaxValueValidator` | ❌ Missing | |
| `StepValueValidator` | ❌ Missing | |
| `DecimalValidator` | ❌ Missing | |
| `FileExtensionValidator` | ❌ Missing | |
| `ProhibitNullCharactersValidator` | ❌ Missing | |
| `validate_email` | ❌ Missing | |
| `validate_slug` | ❌ Missing | |
| `validate_unicode_slug` | ❌ Missing | |
| `validate_ipv4_address` | ❌ Missing | |
| `validate_ipv6_address` | ❌ Missing | |
| `validate_ipv46_address` | ❌ Missing | |
| `validate_integer` | ❌ Missing | |
| `int_list_validator` | ❌ Missing | |

### 1e. Form Rendering

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `as_table()` | ✅ | |
| `as_p()` | ✅ | |
| `as_div()` | ✅ | |
| `as_ul()` | ❌ Missing | |
| `class BaseRenderer` | ❌ Missing | |
| `class DjangoTemplates(renderer)` | ❌ Missing | |
| `class Jinja2(renderer)` | ❌ Missing | |
| `class TemplatesSetting(renderer)` | ❌ Missing | |
| `get_default_renderer()` | ❌ Missing | |

### 1f. FormSets

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BaseFormSet` | ❌ Missing | |
| `class ManagementForm` | ❌ Missing | |
| `formset_factory()` | ❌ Missing | |
| `all_valid(formsets)` | ❌ Missing | |
| `class BaseModelFormSet` | ❌ Missing | |
| `modelformset_factory()` | ❌ Missing | |
| `class BaseInlineFormSet` | ❌ Missing | |
| `inlineformset_factory()` | ❌ Missing | |

### 1g. Model Forms

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BaseModelForm` | ❌ Missing | |
| `class ModelForm` | ❌ Missing | |
| `modelform_factory()` | ❌ Missing | |
| `fields_for_model()` | ❌ Missing | |
| `model_to_dict(instance)` | ❌ Missing | |
| `construct_instance(form, instance)` | ❌ Missing | |
| `class ModelChoiceField` | ❌ Missing | |
| `class ModelMultipleChoiceField` | ❌ Missing | |
| `class ModelChoiceIterator` | ❌ Missing | |

---

## SECTION 2: Auth (`django.contrib.auth`)

### 2a. User Model

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class AbstractUser` | `User` | ⚠️ Partial | |
| `class User(AbstractUser)` | `User` | ✅ | |
| `User.username` | `User::username` | ✅ | |
| `User.password` | `User::password` | ✅ | |
| `User.email` | `User::email` | ✅ | |
| `User.first_name` | `User::first_name` | ✅ | |
| `User.last_name` | `User::last_name` | ✅ | |
| `User.is_staff` | `User::is_staff` | ✅ | |
| `User.is_active` | `User::is_active` | ✅ | |
| `User.is_superuser` | `User::is_superuser` | ✅ | |
| `User.date_joined` | `User::date_joined` | ✅ | |
| `User.last_login` | `User::last_login` | ✅ | |
| `User.groups` | ❌ Missing | M2M with Group |
| `User.user_permissions` | ❌ Missing | M2M with Permission |
| `User.get_username()` | ❌ Missing | |
| `User.get_full_name()` | ❌ Missing | |
| `User.get_short_name()` | ❌ Missing | |
| `User.set_password(raw)` | ❌ Missing | |
| `User.check_password(raw)` | ❌ Missing | |
| `User.set_unusable_password()` | ❌ Missing | |
| `User.has_usable_password()` | ❌ Missing | |
| `User.get_group_permissions()` | ❌ Missing | |
| `User.get_all_permissions()` | ❌ Missing | |
| `User.has_perm(perm, obj)` | ❌ Missing | |
| `User.has_perms(perm_list, obj)` | ❌ Missing | |
| `User.has_module_perms(app_label)` | ❌ Missing | |
| `class AnonymousUser` | `AnonymousUser` | ✅ | |
| `class Permission` | ❌ Missing | Model |
| `class Group` | ❌ Missing | Model |
| `class PermissionsMixin` | Trait | ⚠️ Partial | |
| `class UserManager` | ❌ Missing | create_user, create_superuser |

### 2b. Authentication Backends

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BaseBackend` | `Backend` trait | ⚠️ Partial | |
| `BaseBackend.authenticate(request, **credentials)` | ❌ Missing | |
| `BaseBackend.get_user(user_id)` | ❌ Missing | |
| `BaseBackend.get_user_permissions(user, obj)` | ❌ Missing | |
| `BaseBackend.get_group_permissions(user, obj)` | ❌ Missing | |
| `BaseBackend.get_all_permissions(user, obj)` | ❌ Missing | |
| `BaseBackend.has_perm(user, perm, obj)` | ❌ Missing | |
| `BaseBackend.has_module_perms(user, app_label)` | ❌ Missing | |
| `class ModelBackend(BaseBackend)` | ❌ Missing | DB-backed auth |
| `class AllowAllUsersModelBackend` | ❌ Missing | |
| `class RemoteUserBackend` | ❌ Missing | |
| `authenticate(request, **credentials)` | `AuthBackend::authenticate()` | ⚠️ Partial | |
| `login(request, user)` | ❌ Missing | |
| `logout(request)` | ❌ Missing | |
| `get_user(request)` | `AuthBackend::get_user()` | ⚠️ Partial | |
| `get_user_model()` | ❌ Missing | |
| `update_session_auth_hash(request, user)` | ❌ Missing | |

### 2c. Auth Decorators

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `login_required(function, login_url, redirect_field_name)` | `login_required()` | ✅ | |
| `login_not_required(view_func)` | ❌ Missing | |
| `permission_required(perm, login_url, raise_exception)` | `permission_required()` | ✅ | |
| `user_passes_test(test_func, login_url)` | `user_passes_test()` | ✅ | |
| `require_http_methods(request_method_list)` | `require_http_methods()` | ✅ | |
| `require_POST()` | `require_post()` | ✅ | |
| `require_GET()` | `require_get()` | ✅ | |
| `require_safe()` | ❌ Missing | |

### 2d. Auth Middleware

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class AuthenticationMiddleware` | `SessionAuthMiddleware` | ✅ | Basic version |
| `class LoginRequiredMiddleware` | ❌ Missing | |
| `class RemoteUserMiddleware` | ❌ Missing | |
| `class PersistentRemoteUserMiddleware` | ❌ Missing | |
| `get_user(request)` | `get_user()` | ✅ | |

### 2e. Auth Views

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class LoginView` | `LoginView` | ✅ | Basic |
| `class LogoutView` | `LogoutView` | ✅ | |
| `logout_then_login(request)` | ❌ Missing | |
| `redirect_to_login(next, login_url)` | ❌ Missing | |
| `class PasswordResetView` | ❌ Missing | |
| `class PasswordResetDoneView` | ❌ Missing | |
| `class PasswordResetConfirmView` | ❌ Missing | |
| `class PasswordResetCompleteView` | ❌ Missing | |
| `class PasswordChangeView` | ❌ Missing | |
| `class PasswordChangeDoneView` | ❌ Missing | |

### 2f. Auth Forms

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class AuthenticationForm` | ❌ Missing | |
| `class PasswordResetForm` | ❌ Missing | |
| `class SetPasswordForm` | ❌ Missing | |
| `class PasswordChangeForm` | ❌ Missing | |
| `class UserCreationForm` | ❌ Missing | |
| `class UserChangeForm` | ❌ Missing | |
| `class AdminPasswordChangeForm` | ❌ Missing | |

### 2g. Password Hashing

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class BasePasswordHasher` | | ⚠️ Partial | |
| `class PBKDF2PasswordHasher` | ✅ | |
| `class PBKDF2SHA1PasswordHasher` | ❌ Missing | |
| `class Argon2PasswordHasher` | ❌ Missing | |
| `class BCryptSHA256PasswordHasher` | ✅ | |
| `class BCryptPasswordHasher` | ❌ Missing | |
| `class ScryptPasswordHasher` | ❌ Missing | |
| `class MD5PasswordHasher` | ❌ Missing | |
| `make_password(password, salt, hasher)` | ❌ Missing | |
| `check_password(password, encoded)` | ❌ Missing | |
| `is_password_usable(encoded)` | ❌ Missing | |
| `get_hasher(algorithm)` | ❌ Missing | |

### 2h. Password Validation

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `validate_password(password, user, validators)` | ❌ Missing | |
| `password_changed(password, user)` | ❌ Missing | |
| `password_validators_help_texts()` | ❌ Missing | |
| `class MinimumLengthValidator` | ❌ Missing | |
| `class UserAttributeSimilarityValidator` | ❌ Missing | |
| `class CommonPasswordValidator` | ❌ Missing | |
| `class NumericPasswordValidator` | ❌ Missing | |

---

## SECTION 3: Middleware (`django.middleware`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class CommonMiddleware` | ❌ Missing | URL normalization, APPEND_SLASH |
| `class SecurityMiddleware` | `SecurityMiddleware` | ✅ | |
| `SecurityMiddleware.process_request(request)` | ✅ | |
| `SecurityMiddleware.process_response(request, response)` | ✅ | |
| `class CSRFMiddleware` | `CsrfMiddleware` | ✅ | |
| `CsrfMiddleware.process_request(request)` | ✅ | |
| `CsrfMiddleware.process_response(request, response)` | ✅ | |
| `get_token(request)` | `CsrfMiddleware::get_token()` | ✅ | |
| `rotate_token(request)` | ❌ Missing | |
| `class SessionMiddleware` | `SessionMiddleware` | ✅ | |
| `class MessageMiddleware` | `MessageMiddleware` | ✅ | |
| `class GZipMiddleware` | ❌ Missing | |
| `class ConditionalGetMiddleware` | ❌ Missing | |
| `class LocaleMiddleware` | ❌ Missing | Language detection |
| `class XFrameOptionsMiddleware` | ⚠️ Partial | Included in SecurityMiddleware? |
| `class ContentSecurityPolicyMiddleware` | ❌ Missing | |
| `class UpdateCacheMiddleware` | ❌ Missing | |
| `class FetchFromCacheMiddleware` | ❌ Missing | |
| `class CacheMiddleware` | ❌ Missing | |
| `class BrokenLinkEmailsMiddleware` | ❌ Missing | |

---

## SECTION 4: Sessions (`django.contrib.sessions`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class SessionBase` | `SessionStore` | ⚠️ Partial | |
| `SessionBase.get(key, default)` | ❌ Missing | |
| `SessionBase.__getitem__(key)` | ❌ Missing | |
| `SessionBase.__setitem__(key, value)` | ❌ Missing | |
| `SessionBase.__delitem__(key)` | ❌ Missing | |
| `SessionBase.pop(key)` | ❌ Missing | |
| `SessionBase.keys()` | ❌ Missing | |
| `SessionBase.values()` | ❌ Missing | |
| `SessionBase.items()` | ❌ Missing | |
| `SessionBase.update(dict)` | ❌ Missing | |
| `SessionBase.has_key(key)` | ❌ Missing | |
| `SessionBase.clear()` | ❌ Missing | |
| `SessionBase.flush()` | ❌ Missing | |
| `SessionBase.set_expiry(value)` | ❌ Missing | |
| `SessionBase.get_expiry_age()` | ❌ Missing | |
| `SessionBase.get_expiry_date()` | ❌ Missing | |
| `SessionBase.get_expire_at_browser_close()` | ❌ Missing | |
| `SessionBase.create()` | ❌ Missing | |
| `SessionBase.create_model_instance(data)` | ❌ Missing | |
| `SessionBase.save()` | ❌ Missing | |
| `SessionBase.delete()` | ❌ Missing | |
| `SessionBase.cycle_key()` | ❌ Missing | |
| `SessionStore (DB backend)` | ❌ Missing | |
| `SessionStore (Cache backend)` | ❌ Missing | |
| `SessionStore (File backend)` | ❌ Missing | |
| `SessionStore (Signed cookies)` | ❌ Missing | |

---

## SECTION 5: Messages (`django.contrib.messages`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `add_message(request, level, message, extra_tags)` | `add_message()` | ✅ | |
| `get_messages(request)` | ❌ Missing | |
| `get_level(request)` | ❌ Missing | |
| `set_level(request, level)` | ❌ Missing | |
| `debug(request, message)` | ❌ Missing | |
| `info(request, message)` | ❌ Missing | |
| `success(request, message)` | ❌ Missing | |
| `warning(request, message)` | ❌ Missing | |
| `error(request, message)` | ❌ Missing | |
| `class Message` | `Message` | ✅ | |
| `Message.level` | ❌ Missing | |
| `Message.message` | ✅ | |
| `Message.extra_tags` | ❌ Missing | |
| `class BaseStorage` | ❌ Missing | |
| `class SessionStorage` | ❌ Missing | |
| `class CookieStorage` | ❌ Missing | |
| `class FallbackStorage` | ❌ Missing | |
| `constants: DEBUG, INFO, SUCCESS, WARNING, ERROR` | ✅ | Levels present |

---

## Summary

### Forms: Strong core but missing advanced features
- ✅ Basic fields (Char, Integer, Float, Boolean, Choice, Email, URL)
- ✅ Basic widgets (Text, Number, Email, Password, Hidden, Textarea, Date, DateTime, Select, Radio, Checkbox, File)
- ✅ Form validation and cleaning
- ✅ Form rendering (as_table, as_p, as_div)
- ❌ Missing: DecimalField, DateField, TimeField, DateTimeField in forms
- ❌ Missing: FormSets (entire system)
- ❌ Missing: ModelForms (entire system)
- ❌ Missing: 10+ widget types
- ❌ Missing: Per-field validation hooks

### Auth: Basic user model + decorators, missing admin/crud
- ✅ User model with permissions
- ✅ AnonymousUser
- ✅ Auth backends (basic)
- ✅ Auth middleware (basic)
- ✅ Login/Logout views
- ✅ All decorators (login_required, permission_required, user_passes_test, require_POST/GET)
- ❌ Missing: Permission/Group models
- ❌ Missing: UserManager (create_user, create_superuser)
- ❌ Missing: Password hasher system (has PBKDF2/BCrypt standalone)
- ❌ Missing: Password validation
- ❌ Missing: Auth forms (AuthenticationForm, UserCreationForm, etc.)
- ❌ Missing: Password reset/change views

### Middleware: Session + CSRF + Security done, missing Common/Cache
- ✅ SessionMiddleware
- ✅ CSRFMiddleware
- ✅ SecurityMiddleware
- ✅ MessageMiddleware
- ❌ Missing: CommonMiddleware (APPEND_SLASH, PREPEND_WWW)
- ❌ Missing: GZipMiddleware
- ❌ Missing: Cache middleware
- ❌ Missing: LocaleMiddleware
- ❌ Missing: ContentSecurityPolicyMiddleware

### Sessions: Basic storage, missing backends
- ❌ Missing: SessionBase full API
- ❌ Missing: DB-backed sessions
- ❌ Missing: Cache-backed sessions
- ❌ Missing: File-based sessions
- ❌ Missing: Signed-cookie sessions

### Messages: Basic add_message done, missing retrieval
- ✅ add_message
- ✅ Message struct
- ✅ Constants
- ❌ Missing: get_messages, get_level, set_level
- ❌ Missing: Storage backends
- ❌ Missing: Convenience functions (debug, info, success, warning, error)
