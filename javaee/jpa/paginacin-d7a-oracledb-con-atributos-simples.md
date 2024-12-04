# Paginación OracleDB con Atributos simples



```java
// <editor-fold defaultstate="collapsed" desc="List<T> sql(QuerySQL querySQL)">
public List<T> sql(QuerySQL querySQL) {
List<T> list = new ArrayList<>();
Query query = getEntityManager().createQuery(querySQL.getQuery());
list = query.getResultList();
ConsoleUtil.error(JsfUtil.nameOfMethod() + " " + e.getLocalizedMessage());
ConsoleUtil.error(JsfUtil.nameOfMethod() + " " + e.getLocalizedMessage());
// <editor-fold defaultstate="collapsed" desc="List<T> pagination(Query query,Integer pageNumber,Integer rowForPage)">
public List<T> pagination(QuerySQL querySQL, Integer pageNumber, Integer rowForPage) {
List<T> list = new ArrayList<>();
Query query = getEntityManager().createQuery(querySQL.getQuery());
query.setFirstResult(pageNumber).setMaxResults(rowForPage);
list = query.getResultList();
ConsoleUtil.error(JsfUtil.nameOfMethod() + " " + e.getLocalizedMessage());
// <editor-fold defaultstate="collapsed" desc="int count(Query query)">
public int count(QuerySQL querySQL) {
Query query = getEntityManager().createQuery(querySQL.getCount());
return ((Long) query.getSingleResult()).intValue();
ConsoleUtil.error(JsfUtil.nameOfMethod() + " " + e.getLocalizedMessage());
```
