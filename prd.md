# SHABLLON PRD (Product Requirements Document) — 1 Faqe
**Kursi:** Programimi për Pajisje Mobile (2026/2027) • **Kolegji AAB**  
**Emri i Projektit:** Mr. Clean Mobile Store
**Themeluesi / Ekipi:** [Gresa Bajrami, RE-93932/24]
**Data & Versioni:** Java 02 • Versioni 1.0 (Draft për MVP)

---

## 1. Përdoruesi dhe Problemi Real
- **Kush e përjeton dhimbjen?** 
  Pronari dyqani (Mr. Clean Cleaning Solutions) dhe konsumatorët në Kosovë.
  
- **Kur ndodh?** 
  Çdo ditë - pronari merr porosi përmes Instagram DM, konsumatori nuk mund të porositë 24/7.
  
- **Si e zgjidhin sot?** 
  Pronari: Përgjigjet në Instagram DM (kaotik), mban porosi në letër manuale.
  Konsumatori: Shkon në dyqan ose mesazh, nuk di nëse produkti ka stok.

## 2. Evidenca e Vëzhgimit (3 Bisedat me Përdoruesit)
- **Biseda 1 (Pronari dyqani):** 
  *"Marr 10-15 mesazhe në ditë në Instagram. Nuk mund të shoh të gjithë, ka gabime në porosi."*
  
- **Biseda 2 (Konsumatori):** 
  *"S'e di nëse palloma ka stok përpara se të shkoj në dyqan. Do të porositja online nëse mund."*
  
- **Biseda 3 (Punonjës dyqani):** 
  *"Shitja fizikisht e porosis është lodhje. Nuk e di sa shitje bën ne në ditë."*

## 3. Hipoteza e Vlerës
> Nëse u ofrojmë konsumatorëve PWA mobile me katalog produktesh dhe pronari dyqani i trajton porositë online, atëherë konsumatori do të porositë 24/7, pronari do të kursejë kohë në Instagram, dhe do të ketë statistika shitjesh.

## 4. Rrjedha Kryesore e Përdoruesit (Core Flow — Max 5 Hapa)
1. **Kyçja:** Konsumatori apo pronari kyçet.
2. **Shikimi i Katalogit:** Konsumatori shikon produktet (palloma, detergjente, aroma).
3. **Shtimi në Karrocë:** Zgjedh produktin dhe sasisinë.
4. **Checkout:** Zgjedh mënyrën e pagese (Cash on Delivery ose Bank Transfer).
5. **Porosija:** Pronari merr njoftim dhe konfirmon dorëzimin.

## 5. Kufijtë e MVP-së (Scope Contract)
- **BRENDA MVP-së:**
  1. Autentikimi i thjeshtë.
  2. Katalogi i produkteve (palloma, detergjente, aroma).
  3. Shopping cart dhe checkout (Cash ).
  4. Order history dhe tracking.
  
- **JASHTË MVP-së (Përjashtuara për këtë semestër):**
  - Reviews & Ratings.
  - Stripe payment integration.
  - Video call support.
  - Push notifications.

## 6. Kriteret e Pranimit (Acceptance Criteria)
- [ ] **AC-1:** Konsumatori mund të porositë produkte 24/7.
- [ ] **AC-2:** Pronari merr njoftim për çdo porosi.
- [ ] **AC-3:** Order history shfaqet për të dyja palët.
- [ ] **AC-4:** Aplikacioni funksionon offline (cache).

## 7. Modeli Minimal i të Dhënave (Supabase PostgreSQL)
```sql
users (id, email, full_name, role)
products (id, name, price, category, stock)
orders (id, user_id, total, payment_method, status)
order_items (id, order_id, product_id, quantity)
```

## 8. Rreziku Kryesor që Duhet Testuar
- **Rreziku:** A do të përdorin konsumatorët aplikacionin nëse punon mirë?
- **Testi në Javën 2:** Testim me 5-10 përdorues reale të Mr. Clean.