![Developer गाइड logo](../assets/images/dg_logo.png "OWASP Developer गाइड"){ align=right width="180" }

OWASP Development Guide में आपका स्वागत है।

Open Worldwide Application Security Project ([OWASP][about]) एक गैर-लाभकारी संस्था
(nonprofit foundation) है जो software को सुरक्षा की दिष्टि से बेहतर बनाने के लिए काम करती है।
यह एक open community है जो संगठनों (organizations) को भरोसेमंद applications की कल्पना, विकास,
अधिग्रहण, संचालन और रखरखाव करने के लिए सक्षम बनाता है।

OWASP Top 10 के साथ-साथ, डेवलपर गाइड (Developer Guide) उन मूल संसाधनों में से एक है
जो 2001 में OWASP फाउंडेशन के गठन के तुरंत बाद प्रकाशित हुए थे।
डेवलपर गाइड का संस्करण 1.0 2002 में हुआ था
और तब से विभिन्न [releases][versions] हुए, जो 2005 में संस्करण 2.0 पर पहुंचे।
इसके बाद गाइड को व्यापक रूप से संशोधित किया गया है ताकि ये समय अनुसार प्रासंगिक रहे।
इसका नवीनतम संस्करण 4.x है, क्योंकि संस्करण 3.0 कभी जारी नहीं हुआ।

इस गाइड का उद्देश्य सुरक्षा की अवधारणाओं/बिन्दुओं का परिचय देना तथा application/ system developers के लिए
एक उपयोगी संसाधन प्रदान करना है।
आम तौर पर यह OWASP Software Assurance Maturity Model ([SAMM][samm]) की तर्ज पर सुरक्षा के तरीकों एवं
OWASP [Application Security Wayfinder][intstand] project में दिए projects का वर्णन करता है।

यह गाइड विशिष्ट सुरक्षा विषयों के उत्कृष्ट स्रोतों की नकल करने का प्रयास नहीं करती है;
यह शायद ही कभी किसी विषय पर विस्तार मे जाए, इसके बजाय यह इन सुरक्षा विषयों पर अधिक गहरी जानकारी के लिए
links प्रदान करता है।
इसके बजाय Developer गाइड की सामग्री का लक्ष्य सुलभ होना, प्रायौगिक सुरक्षा विषयों (practical security concepts)
का परिचय देना एवं developers को विभिन्न OWASP tools तथा documents के प्रयोग से अवगत करना है।

इस गाइड में दिए गए सभी OWASP projects तथा tools, free मे download एवं उपयोग के लिए उपलब्ध हैं।
यह सभी OWASP के projects, open source है ; अगर आप application security मे सुधार के इच्छुक हैं तो
आप अवश्य ही हिस्सा ले।

#### लक्षित पाठक

Devlopers को इस OWASP डेवलपर गाइड का प्रयोग ओर अधिक सुरक्षित applications बनाने के लिए करना चाहिए।
यह गाइड सुरक्षा समुदाय (security community) द्वारा लिखी गई है ताकि software developers अच्छी, मजबूत (solid)
एवं सुरक्षित applications बना सकें।
इस गाइड में योगदान देने वाले अधिकांश लोग software developer तथा सुरक्षा इंजीनियर है, जिससे की
इसे developer-centric रखने मे मदद मिलती है।

अगर आप जल्दी में हैं और किसी विशिष्ट विषय पर जानकारी चाहते हैं तो
[OpenCRE chat][opencrechat] LLM को तत्काल उत्तरों के लिए देखे।

#### Developer गाइड क्या है?

इस गाइड को आप OWASP द्वारा devlopers के लिए बनाई, tools एवं documents की पारखी सूची
(cross-reference source) समझ सकते हैं।

_या_ आप इसका उद्देश्य प्रश्नों के उत्तर देने समझ सकते हैं:
"मैं एक devlopers हूँ और मुझे कई security tools एवं गतिविधियों के लिए एक पारखी हुई
गाइड की आवश्यकता है, जिससे मुझे पता है कि मुझे आगे क्या करना चहिए।"

_या_ इसे लेखों के संग्रह के रूप में समझे जो devlopers को application security के व्यापक प्रभाव क्षेत्र से
परिचित कराता हैं।

_या_ इस गाइड को आप OWASP [Integration Standards][intstand] project के साहियोगी दस्तावेज़ के रूप में समझ सकते हैं:
जहाँ Application Security Wayfinder, OWASP के भीतर कई tools, परियोजनाओं एवं दस्तावेज़ों को मैप करता है
वही डेवलपर गाइड इसके लिए कुछ शाब्दिक संदर्भ प्रदान करता है।

[![AppSec Wayfinder](../assets/images/owasp-wayfinder.png "OWASP Application Security Wayfinder")][intstand]

----

OWASP Developer गाइड एक सामुदायिक प्रयास (community effort) है; यदि आपको कुछ बदलने की आवश्यकता लगे तो यहा
[issue submit करे][issue03] या [GitHub पर edit करे][edit03].

[about]: https://owasp.org/about
[edit03]: https://github.com/OWASP/DevGuide/blob/main/docs/index.md
[intstand]: https://owasp.org/projects/integration-standards
[issue03]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2001-introduction
[opencrechat]: https://www.opencre.org/chatbot
[samm]: https://owaspsamm.org/about/
[versions]: https://github.com/OWASP/DevGuide/wiki#old-versions
