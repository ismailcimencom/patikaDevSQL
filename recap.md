1.Film tablosundan 'K' karakteri ile başlayan en uzun ve replacenet_cost u en düşük 4 filmi sıralayınız.  
2.Film tablosunda içerisinden en fazla sayıda film bulunduran rating kategorisi hangisidir?  
3.Cutomer tablosunda en çok alışveriş yapan müşterinin adı nedir?  
4.Category tablosundan kategori isimlerini ve kategori başına düşen film sayılarını sıralayınız.  
5.Film tablosunda isminde en az 4 adet 'e' veya 'E' karakteri bulunan kaç tane film vardır?  

1.**SELECT** title,replacement_cost,length **FROM** film  
**WHERE** title **LIKE** 'K%'   
**ORDER BY** length **DESC**, replacement_cost **ASC**  

2.**SELECT** rating **FROM** film  
**GROUP BY** rating  
**ORDER BY** rating **DESC**  
**LIMIT** 1	  

3.**SELECT** customer.first_name **FROM** customer  
**JOIN** payment **ON** customer.customer_id = payment.customer_id  
**GROUP BY** first_name  
**ORDER BY COUNT**(*) **DESC**  
**LIMIT** 1  

4.**SELECT** name, **COUNT**(name) FROM category  
**JOIN** film_category **ON** film_category.category_id = category.category_id  
**JOIN** film **ON** film.film_id = film_category.film_id  
**GROUP BY** name  
**ORDER BY COUNT**(name) **DESC**  

5.**SELECT COUNT**(title) **FROM** film  
**WHERE** title **ILIKE** '%e%e%e%e%' 

<details> <summary> MySQL </summary>
  SELECT COUNT(title) FROM film  
  WHERE title LIKE '%e%e%e%e%' 
</details>
