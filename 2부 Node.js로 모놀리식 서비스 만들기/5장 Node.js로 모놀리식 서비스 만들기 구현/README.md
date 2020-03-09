# 5장. Node.js로 모놀리식 서비스 만들기 : 구현

- url.parse(urlStr, [parseQueryString], [slashesDenoteHost])
  - url 문자열(urlStr)을 url 객체로 변환하여 반환. (parseQueryString, slashesDenoteHost의 기본값 false)
  - parseQueryString
    - true : url 객체의 query 속성을 객체 형식으로 가져옴. (querystring 모듈 사용 querystring.parse가 쿼리 문자열을 쿼리 객체로 바꿔줌)
    - false : url 객체의 query 속성을 문자열 형식으로 가져옴.
  - slashesDenoteHost
    - true : urlStr이 '//foo/bar' 인 경우 foo는 host, /bar는 path로 인식
    - false : urlStr이 '//foo/bar' 인 경우 //foo/bar 전체를 path로 인식하고 host는 null이다.