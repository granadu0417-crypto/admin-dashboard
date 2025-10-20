# 웹사이트 배포 필수 체크리스트

> **모든 새 홈페이지 제작 시 반드시 포함할 항목들**

---

## 📊 Google Analytics 4 (GA4)

### 측정 ID
```
G-TWVG616XGC
```

### 속성 ID
```
508989566
```

### HTML 헤드에 추가할 코드
```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-TWVG616XGC"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-TWVG616XGC');
</script>
```

**위치:** `</head>` 태그 바로 앞

---

## 🗺️ sitemap.xml

### 템플릿 (정적 사이트용)
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://YOUR-SITE.pages.dev/</loc>
    <lastmod>2025-10-20</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
  <!-- 추가 페이지들 -->
</urlset>
```

**파일 위치:** `/sitemap.xml` (루트)

**Google Search Console 등록:**
- https://search.google.com/search-console
- 속성 추가 → sitemap.xml URL 제출

---

## 🤖 robots.txt

### 템플릿
```txt
User-agent: *
Allow: /

Sitemap: https://YOUR-SITE.pages.dev/sitemap.xml
```

**파일 위치:** `/robots.txt` (루트)

---

## 🏷️ SEO Meta Tags

### 필수 메타 태그
```html
<head>
  <!-- 기본 메타 -->
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="사이트 설명 (150-160자)">
  <meta name="keywords" content="키워드1, 키워드2, 키워드3">
  <meta name="author" content="granadu">

  <!-- Open Graph (소셜 미디어) -->
  <meta property="og:type" content="website">
  <meta property="og:title" content="페이지 제목">
  <meta property="og:description" content="사이트 설명">
  <meta property="og:url" content="https://YOUR-SITE.pages.dev/">
  <meta property="og:image" content="https://YOUR-SITE.pages.dev/og-image.jpg">

  <!-- Twitter Card -->
  <meta name="twitter:card" content="summary_large_image">
  <meta name="twitter:title" content="페이지 제목">
  <meta name="twitter:description" content="사이트 설명">
  <meta name="twitter:image" content="https://YOUR-SITE.pages.dev/og-image.jpg">

  <!-- Favicon -->
  <link rel="icon" type="image/x-icon" href="/favicon.ico">
  <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
</head>
```

---

## 🎨 필수 파일

### 1. favicon.ico
- **크기:** 16x16, 32x32, 48x48
- **위치:** `/favicon.ico`
- **생성 도구:** https://realfavicongenerator.net/

### 2. apple-touch-icon.png
- **크기:** 180x180
- **위치:** `/apple-touch-icon.png`

### 3. og-image.jpg
- **크기:** 1200x630 (권장)
- **위치:** `/og-image.jpg`
- **용도:** 소셜 미디어 공유 시 표시

---

## ⚡ Cloudflare Pages 설정

### _headers 파일
```
/*
  X-Frame-Options: SAMEORIGIN
  X-Content-Type-Options: nosniff
  X-XSS-Protection: 1; mode=block
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: geolocation=(), microphone=(), camera=()
```

**파일 위치:** `/public/_headers`

### _redirects 파일 (필요시)
```
/old-page  /new-page  301
```

---

## ✅ 배포 전 체크리스트

- [ ] GA4 코드 추가 (G-TWVG616XGC)
- [ ] sitemap.xml 생성 및 URL 업데이트
- [ ] robots.txt 생성 및 sitemap URL 업데이트
- [ ] Meta description 작성 (150-160자)
- [ ] Meta keywords 작성
- [ ] OG 태그 설정 (제목, 설명, 이미지)
- [ ] favicon.ico 추가
- [ ] apple-touch-icon.png 추가
- [ ] og-image.jpg 추가
- [ ] _headers 파일 추가
- [ ] 모바일 반응형 확인
- [ ] 크로스 브라우저 테스트 (Chrome, Safari, Firefox)
- [ ] 페이지 로딩 속도 확인 (PageSpeed Insights)
- [ ] 404 에러 페이지 생성
- [ ] HTTPS 적용 확인

---

## 🔍 배포 후 확인 사항

### 1. Google Search Console
- [ ] 속성 등록
- [ ] sitemap.xml 제출
- [ ] 색인 생성 요청

### 2. Google Analytics
- [ ] 실시간 데이터 확인 (사이트 방문 후 5분)
- [ ] 호스트 이름 확인 (탐색 분석)

### 3. 성능 테스트
- [ ] PageSpeed Insights: https://pagespeed.web.dev/
- [ ] GTmetrix: https://gtmetrix.com/
- [ ] 목표: 90점 이상

### 4. SEO 검증
- [ ] Meta 태그 확인: https://www.heymeta.com/
- [ ] 구조화된 데이터 테스트: https://search.google.com/test/rich-results

---

## 📝 사이트별 정보 기록

| 항목 | 정보 |
|------|------|
| **사이트명** | |
| **URL** | https://*.pages.dev |
| **배포일** | YYYY-MM-DD |
| **GA4 확인** | ✅ / ❌ |
| **Search Console** | ✅ / ❌ |
| **Sitemap 제출** | ✅ / ❌ |

---

## 🔗 유용한 링크

- **Google Analytics:** https://analytics.google.com
- **Google Search Console:** https://search.google.com/search-console
- **Cloudflare Pages:** https://dash.cloudflare.com/
- **Admin Dashboard:** https://admin-dashboard-210.pages.dev/

---

**마지막 업데이트:** 2025-10-20
