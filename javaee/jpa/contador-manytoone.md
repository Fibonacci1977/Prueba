# Contador @ManyToOne



```java
public int countBancoIdAndActivo(Banco BANCOID, String ACTIVO) {
List<Cajero> list = new ArrayList<>();
try {
​
Query query = em.createQuery("SELECT COUNT(c) FROM Cajero c WHERE c.BANCOID = :BANCOID AND c.ACTIVO = :ACTIVO ");
​
query.setParameter("BANCOID", BANCOID).setParameter("ACTIVO", ACTIVO).getResultList();
return ((Long) query.getSingleResult()).intValue();
​
} catch (Exception ex) {
JsfUtil.errorMessage(JsfUtil.nameOfMethod() + " " + ex.getLocalizedMessage());
}
```
