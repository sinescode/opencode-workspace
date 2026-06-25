# Django 6.0.6 ORM — Feature Comparison with Rjango

> **Django modules analyzed:** `django.db.models`, `django.db.models.fields`, `django.db.models.functions`, `django.db.backends`, `django.db.migrations`

---

## 1. Model System (`django.db.models`)

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Model` | `Model` (trait) | ⚠️ Partial | Rjango uses trait not class |
| `Model.save()` | ❌ Missing | |
| `Model.save(force_insert, force_update, using, update_fields)` | ❌ Missing | |
| `Model.delete()` | ❌ Missing | |
| `Model.refresh_from_db()` | ❌ Missing | |
| `Model.get_absolute_url()` | ❌ Missing | |
| `Model.__str__()` | ❌ Missing | |
| `Model.pk` | `Model::get_pk()` | ✅ | Present |
| `Model.id` | ❌ Missing | Default pk alias |
| `Model.objects` | `Model::objects()` | ✅ | Manager access |
| `Model._meta` | `Model::meta()` | ⚠️ Partial | Rjango has basic metadata |
| `Model.DoesNotExist` | ❌ Missing | |
| `Model.MultipleObjectsReturned` | ❌ Missing | |
| `class ModelState` | ❌ Missing | |
| `class ModelStateFieldsCacheDescriptor` | ❌ Missing | |
| `class DEFERRED` | ❌ Missing | |
| `class AltersData` | ❌ Missing | |

---

## 2. Fields

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Field` | `Field` | ✅ | Present |
| `Field.null` | `Field::null` | ✅ | |
| `Field.blank` | ❌ Missing | |
| `Field.choices` | ❌ Missing | |
| `Field.db_column` | ❌ Missing | |
| `Field.db_index` | ❌ Missing | |
| `Field.db_tablespace` | ❌ Missing | |
| `Field.default` | ❌ Missing | |
| `Field.editable` | ❌ Missing | |
| `Field.error_messages` | ❌ Missing | |
| `Field.help_text` | ❌ Missing | |
| `Field.primary_key` | `Field::primary_key` | ✅ | |
| `Field.unique` | `Field::unique` | ✅ | |
| `Field.verbose_name` | ❌ Missing | |
| `Field.validators` | `Field::validators` | ✅ | |
| `class AutoField` | ❌ Missing | |
| `class BigAutoField` | `AutoField` | ❌ Wrong type name |
| `class SmallAutoField` | ❌ Missing | |
| `class CharField(max_length)` | `CharField` | ✅ | |
| `class TextField` | `TextField` | ✅ | |
| `class IntegerField` | `IntegerField` | ✅ | |
| `class BigIntegerField` | ❌ Missing | |
| `class SmallIntegerField` | ❌ Missing | |
| `class PositiveIntegerField` | ❌ Missing | |
| `class PositiveBigIntegerField` | ❌ Missing | |
| `class PositiveSmallIntegerField` | ❌ Missing | |
| `class BooleanField` | `BooleanField` | ✅ | |
| `class NullBooleanField` | ❌ Missing | |
| `class FloatField` | `FloatField` | ✅ | |
| `class DecimalField(max_digits, decimal_places)` | ❌ Missing | |
| `class DateTimeField` | `DateTimeField` | ✅ | |
| `class DateField` | `DateField` | ✅ | |
| `class TimeField` | ❌ Missing | |
| `class DurationField` | ❌ Missing | |
| `class FileField` | ❌ Missing | |
| `class ImageField` | ❌ Missing | |
| `class FilePathField` | ❌ Missing | |
| `class SlugField` | ❌ Missing | |
| `class URLField` | ❌ Missing | |
| `class EmailField` | ❌ Missing | |
| `class UUIDField` | ❌ Missing | |
| `class BinaryField` | ❌ Missing | |
| `class IPAddressField` | ❌ Missing | |
| `class GenericIPAddressField` | ❌ Missing | |
| `class CommaSeparatedIntegerField` | ❌ Missing | |
| `class JSONField` | ❌ Missing | |
| `class Field.clean(value, model_instance)` | ❌ Missing | |
| `class Field.formfield()` | ❌ Missing | |
| `class Field.value_from_object(obj)` | ❌ Missing | |
| `class Field.pre_save(model_instance, add)` | ❌ Missing | |
| `class Field.get_db_prep_value(value, connection)` | ❌ Missing | |

---

## 3. Relationships

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class ForeignKey(to, on_delete)` | `ForeignKey` | ✅ | Present |
| `ForeignKey.related_name` | ❌ Missing | |
| `ForeignKey.related_query_name` | ❌ Missing | |
| `ForeignKey.limit_choices_to` | ❌ Missing | |
| `ForeignKey.to_field` | ❌ Missing | |
| `ForeignKey.db_constraint` | ❌ Missing | |
| `ForeignKey.on_delete` (CASCADE, PROTECT, SET_NULL, etc.) | ⚠️ Partial | Basic on_delete |
| `class OneToOneField(to, on_delete)` | `OneToOneField` | ✅ | Present |
| `class ManyToManyField(to)` | `ManyToManyField` | ✅ | Present |
| `ManyToManyField.through` | ❌ Missing | |
| `ManyToManyField.through_fields` | ❌ Missing | |
| `ManyToManyField.db_table` | ❌ Missing | |
| `ManyToManyField.symmetrical` | ❌ Missing | |
| `class ForeignObject` | ❌ Missing | Base for all relations |
| `class ForeignObjectRel` | ❌ Missing | Reverse relation |
| `class ManyToOneRel` | ❌ Missing | |
| `class ManyToManyRel` | ❌ Missing | |
| `class OneToOneRel` | ❌ Missing | |
| `class GenericForeignKey` | ❌ Missing | |
| `class GenericRelation` | ❌ Missing | |

---

## 4. Managers & QuerySets

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Manager` | `Manager` (trait) | ⚠️ Partial | Rjango uses trait |
| `Manager.get_queryset()` | ❌ Missing | |
| `Manager.all()` | ❌ Missing | |
| `Manager.filter(**kwargs)` | `Manager::filter()` | ✅ | |
| `Manager.exclude(**kwargs)` | ❌ Missing | |
| `Manager.annotate(**kwargs)` | ❌ Missing | |
| `Manager.order_by(*fields)` | ❌ Missing | |
| `Manager.values(*fields)` | ❌ Missing | |
| `Manager.values_list(*fields)` | ❌ Missing | |
| `Manager.distinct()` | ❌ Missing | |
| `Manager.get(**kwargs)` | ❌ Missing | |
| `Manager.create(**kwargs)` | ❌ Missing | |
| `Manager.update(**kwargs)` | ❌ Missing | |
| `Manager.delete()` | ❌ Missing | |
| `Manager.count()` | ❌ Missing | |
| `Manager.exists()` | ❌ Missing | |
| `Manager.first()` | ❌ Missing | |
| `Manager.last()` | ❌ Missing | |
| `class QuerySet` | `Query` builder | ⚠️ Partial | Rjango has SQL builder but not full QuerySet API |
| `QuerySet.filter()` | `Query::filter()` | ✅ | |
| `QuerySet.exclude()` | ❌ Missing | |
| `QuerySet.annotate()` | ❌ Missing | |
| `QuerySet.order_by()` | ❌ Missing | |
| `QuerySet.values()` | ❌ Missing | |
| `QuerySet.select_related()` | ❌ Missing | |
| `QuerySet.prefetch_related()` | ❌ Missing | |
| `QuerySet.defer()` | ❌ Missing | |
| `QuerySet.only()` | ❌ Missing | |
| `QuerySet.using(alias)` | ❌ Missing | |
| `QuerySet.select_for_update()` | ❌ Missing | |
| `QuerySet.iterator(chunk_size)` | ❌ Missing | |
| `QuerySet.aggregate()` | ❌ Missing | |
| `QuerySet.union()` | ❌ Missing | |
| `QuerySet.intersection()` | ❌ Missing | |
| `QuerySet.difference()` | ❌ Missing | |
| `QuerySet[:n]` slicing | ❌ Missing | |
| `QuerySet.exists()` | ❌ Missing | |
| `QuerySet.count()` | ❌ Missing | |
| `QuerySet.update()` | ❌ Missing | |
| `QuerySet.delete()` | ❌ Missing | |
| `QuerySet.create()` | ❌ Missing | |
| `QuerySet.get_or_create()` | ❌ Missing | |
| `QuerySet.update_or_create()` | ❌ Missing | |
| `QuerySet.bulk_create()` | ❌ Missing | |
| `QuerySet.bulk_update()` | ❌ Missing | |
| `QuerySet.in_bulk()` | ❌ Missing | |
| `QuerySet.latest(field)` | ❌ Missing | |
| `QuerySet.earliest(field)` | ❌ Missing | |
| `class Prefetch(lookup, queryset, to_attr)` | ❌ Missing | |
| `class RawQuerySet` | ❌ Missing | |

---

## 5. Query Expressions

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Expression` | `Expression` | ⚠️ Partial | Rjango has basic expression trait |
| `class Subquery(queryset)` | ❌ Missing | |
| `class Exists(queryset)` | ❌ Missing | |
| `class OuterRef(field)` | ❌ Missing | |
| `class F(field)` | ❌ Missing | |
| `class Q(*args, **kwargs)` | `Q` | ✅ | Present |
| `Q.AND` | `Q::And` | ✅ | |
| `Q.OR` | `Q::Or` | ✅ | |
| `Q.NOT` | `Q::Not` | ✅ | |
| `class Value(value, output_field)` | ❌ Missing | |
| `class Func(*expressions)` | ❌ Missing | |
| `class Case(*cases, default, output_field)` | ❌ Missing | |
| `class When(condition, then)` | ❌ Missing | |
| `class Window(expression, partition_by, order_by)` | ❌ Missing | |
| `class OrderBy(expression, descending, nulls_first)` | ❌ Missing | |

---

## 6. Aggregates

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Aggregate` | ❌ Missing | |
| `Avg(expression)` | ❌ Missing | |
| `Count(expression)` | ❌ Missing | |
| `Max(expression)` | ❌ Missing | |
| `Min(expression)` | ❌ Missing | |
| `Sum(expression)` | ❌ Missing | |
| `StdDev(expression)` | ❌ Missing | |
| `Variance(expression)` | ❌ Missing | |
| `AnyValue(expression)` | ❌ Missing | |
| `StringAgg(expression, delimiter)` | ❌ Missing | |

Note: Rjango has `Sum`, `Count`, `Avg`, `Min`, `Max` as standalone structs in `expressions.rs` but they're not integrated with the query builder.

---

## 7. Lookups

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Lookup` | ❌ Missing | |
| `exact` | ❌ Missing | |
| `iexact` | ❌ Missing | |
| `contains` | ❌ Missing | |
| `icontains` | ❌ Missing | |
| `in` | ❌ Missing | |
| `gt` | ❌ Missing | |
| `gte` | ❌ Missing | |
| `lt` | ❌ Missing | |
| `lte` | ❌ Missing | |
| `startswith` | ❌ Missing | |
| `istartswith` | ❌ Missing | |
| `endswith` | ❌ Missing | |
| `iendswith` | ❌ Missing | |
| `range` | ❌ Missing | |
| `date` | ❌ Missing | |
| `year` | ❌ Missing | |
| `month` | ❌ Missing | |
| `day` | ❌ Missing | |
| `week` | ❌ Missing | |
| `week_day` | ❌ Missing | |
| `iso_week_day` | ❌ Missing | |
| `quarter` | ❌ Missing | |
| `time` | ❌ Missing | |
| `hour` | ❌ Missing | |
| `minute` | ❌ Missing | |
| `second` | ❌ Missing | |
| `isnull` | ❌ Missing | |
| `regex` | ❌ Missing | |
| `iregex` | ❌ Missing | |

---

## 8. Database Backends

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| SQLite | `SQLiteBackend` | ✅ | Present |
| PostgreSQL | `PostgreSQLBackend` | ✅ | Present |
| MySQL | `MySQLBackend` | ✅ | Present |
| Oracle | ❌ Missing | |
| `class BaseDatabaseWrapper` | `Backend` trait | ⚠️ Partial | |
| `BaseDatabaseWrapper.execute(query, params)` | ❌ Missing | |
| `BaseDatabaseWrapper.cursor()` | ❌ Missing | |
| `BaseDatabaseWrapper.create_table(model)` | ❌ Missing | |
| `schema_editor` | ❌ Missing | |
| `class BaseDatabaseFeatures` | ❌ Missing | |
| `class BaseDatabaseOperations` | ❌ Missing | |
| `class BaseDatabaseIntrospection` | ❌ Missing | |
| `class BaseDatabaseClient` | ❌ Missing | |
| `class BaseDatabaseCreation` | ❌ Missing | |
| `class BaseDatabaseSchemaEditor` | ❌ Missing | |

---

## 9. Model Options / Meta

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Options` | `ModelMeta` | ⚠️ Partial | |
| `Options.db_table` | `ModelMeta::table_name` | ✅ | |
| `Options.verbose_name` | ❌ Missing | |
| `Options.verbose_name_plural` | ❌ Missing | |
| `Options.ordering` | ❌ Missing | |
| `Options.unique_together` | ❌ Missing | |
| `Options.indexes` | ❌ Missing | |
| `Options.constraints` | ❌ Missing | |
| `Options.get_fields()` | ❌ Missing | |
| `Options.get_field(name)` | ❌ Missing | |
| `Options.app_label` | ❌ Missing | |

---

## 10. Indexes & Constraints

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Index(name, fields)` | ❌ Missing | |
| `class UniqueConstraint(fields, name, condition)` | ❌ Missing | |
| `class CheckConstraint(check, name)` | ❌ Missing | |
| `class Deferrable` | ❌ Missing | |
| `class ExclusionConstraint` | ❌ Missing | |

---

## 11. Migrations

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `Migration` class | ❌ Missing | |
| `class CreateModel(name, fields)` | ✅ | Present |
| `class DeleteModel(name)` | ✅ | Present |
| `class AddField(model, field)` | ✅ | Present |
| `class RemoveField(model, name)` | ✅ | Present |
| `class AlterField(model, name, field)` | ✅ | Present |
| `class RenameField(model, old, new)` | ✅ | Present |
| `class RenameModel(old, new)` | ❌ Missing | |
| `class AlterModelTable(name, table)` | ❌ Missing | |
| `class AlterModelTableComment(name, comment)` | ❌ Missing | |
| `class AlterUniqueTogether(name, unique_together)` | ❌ Missing | |
| `class AlterIndexTogether(name, index_together)` | ❌ Missing | |
| `class AlterModelOptions(name, options)` | ❌ Missing | |
| `class AlterOrderWithRespectTo(name, order)` | ❌ Missing | |
| `class AlterModelManagers(name, managers)` | ❌ Missing | |
| `class AddIndex(model, index)` | ❌ Missing | |
| `class RemoveIndex(model, name)` | ❌ Missing | |
| `class RenameIndex(model, old, new)` | ❌ Missing | |
| `class AddConstraint(model, constraint)` | ❌ Missing | |
| `class RemoveConstraint(model, name)` | ❌ Missing | |
| `class AlterConstraint(model, name, constraint)` | ❌ Missing | |
| `class SeparateDatabaseAndState(database, state)` | ❌ Missing | |
| `class RunSQL(sql, reverse_sql)` | ❌ Missing | |
| `class RunPython(code, reverse_code)` | ❌ Missing | |
| `Autodetector` | `MigrationDetector` | ⚠️ Partial | |
| `MigrationExecutor` | ❌ Missing | |
| `MigrationLoader` | ❌ Missing | |
| `MigrationRecorder` | ❌ Missing | |
| `MigrationQuestioner` | ❌ Missing | |
| `MigrationWriter` | ❌ Missing | |
| `Migrate command` | `migrate` command | ⚠️ Partial | CLI exists |
| `Makemigrations command` | `makemigrations` command | ⚠️ Partial | CLI exists |

---

## 12. Model Functions

| Django API | Rjango Equivalent | Status | Notes |
|---|---|---|---|
| `class Coalesce(*expressions)` | ❌ Missing | |
| `class Concat(*expressions)` | ❌ Missing | |
| `class Greatest(*expressions)` | ❌ Missing | |
| `class Least(*expressions)` | ❌ Missing | |
| `class Length(expression)` | ❌ Missing | |
| `class Lower(expression)` | ❌ Missing | |
| `class Upper(expression)` | ❌ Missing | |
| `class StrIndex(string, substring)` | ❌ Missing | |
| `class Substr(expression, pos, length)` | ❌ Missing | |
| `class Trim(expression)` | ❌ Missing | |
| `class Replace(expression, text, replacement)` | ❌ Missing | |
| `class Cast(expression, output_field)` | ❌ Missing | |
| `class ExtractYear(expression)` | ❌ Missing | |
| `class ExtractMonth(expression)` | ❌ Missing | |
| `class ExtractDay(expression)` | ❌ Missing | |
| `class ExtractWeekDay(expression)` | ❌ Missing | |
| `class ExtractQuarter(expression)` | ❌ Missing | |
| `class Now()` | ❌ Missing | |
| `class TruncDate(expression)` | ❌ Missing | |
| `class TruncYear(expression)` | ❌ Missing | |
| `class TruncMonth(expression)` | ❌ Missing | |

---

## Summary

### ORM Features in Rjango (✅ / ⚠️ Partial)
- ✅ Field types: `AutoField`, `CharField`, `TextField`, `IntegerField`, `FloatField`, `BooleanField`, `DateTimeField`, `DateField`, `BinaryField`
- ✅ Relationship fields: `ForeignKey`, `OneToOneField`, `ManyToManyField`
- ✅ `Field` trait with `null`, `unique`, `primary_key`, `validators`
- ⚠️ `Manager` trait with `filter()` method
- ⚠️ `Query` builder with SQL generation for basic queries
- ⚠️ `Q` expression with AND/OR/NOT
- ⚠️ Basic aggregate definitions (Sum, Count, Avg, Min, Max)
- ⚠️ Database backends: SQLite, PostgreSQL, MySQL
- ⚠️ `ModelMeta` with `table_name`, `fields`
- ⚠️ Migration operations: CreateModel, DeleteModel, AddField, RemoveField, AlterField, RenameField
- ⚠️ Migration detection (basic autodetector)
- ✅ CLI commands: `migrate`, `makemigrations`, `showmigrations`

### Missing ORM Features (❌)
- ❌ Real database CRUD (create/read/update/delete via models)
- ❌ Full QuerySet API (chaining, lazy evaluation, slicing, aggregation)
- ❌ Field lookups (exact, contains, gt, lt, in, range, date, year, etc.)
- ❌ Aggregation on QuerySets
- ❌ `F()` expressions for database-side updates
- ❌ `Subquery` / `Exists` / `OuterRef`
- ❌ `Func` / `Value` / `Case` / `When` / `Window` expressions
- ❌ `SelectRelated` / `PrefetchRelated` for eager loading
- ❌ `annotate()` / `alias()` / `values()` / `values_list()`
- ❌ Model signals (pre_save, post_save, pre_delete, post_delete, m2m_changed)
- ❌ Model `save()` / `delete()` / `refresh_from_db()`
- ❌ Indexes & constraints
- ❌ Schema editor / table creation from models
- ❌ Migration executor / state tracking
- ❌ Migration loading from files
- ❌ Most model functions (Coalesce, Concat, Length, Cast, Extract, Trunc, etc.)
- ❌ Model validation via `full_clean()` / `clean()`
- ❌ `get_or_create` / `update_or_create` / `bulk_create` / `bulk_update`
- ❌ Transaction management (`atomic()`, commit, rollback, savepoint)
- ❌ `select_for_update()` / row-level locking
- ❌ Router support (multiple databases)
- ❌ `defer()` / `only()` for deferred fields
- ❌ `union()` / `intersection()` / `difference()` for set operations
- ❌ Oracle database backend
- ❌ `EnumField` / `Choices` integration
- ❌ Migration recorder (django_migrations table)
- ❌ Migration writer (file generation)
- ❌ Migration optimizer
- ❌ Model inheritance (abstract base, multi-table, proxy)
