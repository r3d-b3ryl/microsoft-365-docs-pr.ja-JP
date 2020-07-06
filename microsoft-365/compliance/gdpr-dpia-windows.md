---
title: GDPR のための Windows 向け DPIA データ プロセッサー サービス
description: Windows 向けデータ プロセッサー サービス を使用するときに、データ保護影響評価 (DPIA) が必要かどうかを判断する情報を見つけます。
keywords: DPIA、Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: c594bbca6383874346719a477d3f86f3dac99409
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023623"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-data-processor-service-for-windows"></a>データ保護影響評価: Windows 向け Microsoft データ プロセッサー サービスを利用するデータ管理者向けガイダンス

>[!NOTE]
>このトピックは、Windows プレビュー プログラムの参加者を対象としており、特定の使用条件に同意することが要求されています。 プログラムの詳細を確認し、使用条件に同意するには、[https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview) を参照してください。

一般データ保護規則 (GDPR) では、データ管理者は「自然人の権利と自由を危険にさらす可能性が高い」操作処理に関してデータ保護影響評価 (DPIA) を作成することが要求されています。 Windows 向けデータ プロセッサー サービス自体には、それを使用するデータ管理者による DPIA の作成を要求する要素が含まれているわけではありません。 DPIAI が必要かどうかは、データ管理者が Windows 向けデータ プロセッサー サービスを展開、構成、使用する方法の詳細と文脈によって決まります。 

このドキュメントは、DPIA が必要であるかどうかを判断し、必要な場合には DPIA に含める詳細情報を決定する上で役立つ、Windows 向けデータ プロセッサー サービスに関する情報をデータ管理者に提供することを目的としています。

>[!Note]
>Microsoft はこのドキュメントでいかなる法的助言も提供いたしません。 このドキュメントは、情報提供のみを目的として提供されています。 Windows 向けデータ プロセッサー サービスまたはその他の Microsoft オンラインサービスの使用に関しての DPIA の必要性および内容を判断するにあたり、お客様はプライバシー責任者または弁護士と連携することをお勧めします。

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>パート 1 – DPIA が必要であるかどうかの判断

GDPR の第 35 条では、「特に新たな技術を用いるなどのある種の処理が、その性質、範囲、文脈および処理の目的を考慮して、自然人の権利や自由に高リスクを生じさせる可能性がある場合」に、データ管理者がデータ保護影響評価 (DPIA) を作成することが義務付けられています。 さらに、そのような高いリスクを示す具体的な因子も規定されています。これらの因子は次の表で説明します。 データ管理者は、DPIA が必要かどうかを判断するにあたり、管理者による Windows 向けデータ プロセッサー サービスの具体的な実装方法と使用方法に照らして、これらの因子とともにその他の関連する因子を検討する必要があります。

## <a name="table-1--data-processor-service-for-windows-dpia-risk-factors"></a>表 1 - Windows 向けデータ プロセッサー サービスの DPIA リスク因子 

|||
|:----|:----|
|**高リスク因子**|**Windows 向けデータ プロセッサー サービスに関連する情報**|
| プロファイリングを含めた自動処理に基づいて自然人に関する個人的側面を体系的かつ広範囲に評価され、その評価に基づいて決定がなされ、その決定が自然人に関する法的効果を生じさせるかまたは同様に自然人に重大な影響を与える場合。 |Windows 向けデータ プロセッサー サービスには、特定のデータ自動処理を実行するための機能がありません。<br><br> ただし、Windows 向けデータ プロセッサー サービスは他のサービスでデータ ソースとして使用されているため、データ管理者はこれらのサービスを構成してそのような処理のために使用できる可能性があります。 管理者は、Windows 向けデータ プロセッサー サービスに接続されているサービスを管理者がどの程度使用しているかによって、この決定を行う必要があります。|   
| 特別な種類のデータ (人種または民族的素性、政治的思想、宗教的または哲学的信条、あるいは労働組合員資格に関する個人データの処理、および遺伝データ、自然人の一意な識別を目的とした生体データ、健康に関するデータまたは自然人の性生活あるいは性的指向に関するデータ)、または有罪判決および犯罪に関する個人データを大規模に処理する場合。 | Windows 向けデータ プロセッサー サービスは、特別な種類の個人データを処理するようには設計されておらず、Windows 向けデータ プロセッサー サービスを使用することで管理者による処理に伴うリスクが高まることはありません。<br><br> ただし、データ処理者は、Windows 向けデータ プロセッサー サービスに接続されているサービスを使用して、列挙された特別な種類のデータを処理することができます。 Windows 向けデータ プロセッサー サービスをデータ ソースとして使用するサービスは、特別な種類の個人データを含め、あらゆる種類のデータを顧客が追跡または処理できるようにすることが可能です。 ただし、データ処理者である Microsoft にはそのような利用を制御する能力はなく、そのような利用に関する情報もほとんど持っていません。 データ管理者のデータの適切な使用方法を決定することは、データ管理者の義務です。 |

## <a name="part-2--contents-of-a-dpia"></a>パート 2 - DPIA の内容 

Article 35(7) mandates that a Data Protection Impact Assessment specify the purposes of processing and a systematic description of the envisioned processing. A systematic description of a comprehensive DPIA might include factors such as the types of data processed, how long data is retained, where the data is located and transferred, and what third parties may have access to the data. In addition, the DPIA must include: 

目的に関する処理作業の必要性および比例性の評価 

自然人の権利および自由に関するリスクの評価 

リスクに対処するために予定された対策。データ主体および関連する他者の権利および正当な利益を考慮し、個人データの保護を確実にし、本規則の遵守を証明するための保護措置、安全対策および安全メカニズムを含む。 

下の表には、これらの各要素に関係があるWindows 向けデータ プロセッサー サービスに関する情報を示します。 パート 1 と同様に、データ管理者は下記の詳細情報とその他の関連要素について、データ管理者による Windows 向けデータ プロセッサー サービスの具体的な実装方法と使用方法の観点から検討する必要があります。 

## <a name="table-2--data-processor-service-for-windows-dpia-elements"></a>表 2 - Windows 向けデータ プロセッサー サービスの DPIA 要素 

||||
|:---|:---|:--|
|**DPIA の要素**|**Windows 向けデータ プロセッサー サービスに関連する情報**| |
| 処理の目的 | Windows 向け サービスを使用したデータ処理の目的は、このサービスを実装、構成、使用する管理者が決定します。 <br><br> 「[オンライン サービスの使用条件 (OST)](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)」 に定められているように、Microsoft はデータ処理者として、お客様 (データ管理者) に対し要求されたサービスを提供する目的でのみ顧客データを処理します。 顧客データまたは顧客データから得られた情報を、Microsoft が広告およびその他の類似する商用目的で使用することはありません。 |
| 処理される個人データのカテゴリ | **顧客データ** - これは、顧客または顧客の代理が エンタープライズ サービスの使用を通じて Microsoft に提供する、テキスト、音声、ビデオ、画像ファイル、およびソフトウェアを含むすべてのデータのことです。 顧客データには、エンド ユーザーに関する特定可能な情報 (Azure Active Directory でのユーザー名や連絡先情報、Windows 診断データからのデバイス情報など) が含まれます。 <br><br> **システム生成データ** - Microsoft がエンタープライズ サービスをユーザーに提供する上で役立つ、Microsoft が生成するデータ。 システム生成データには主に固有 ID などの仮名化データが含まれています。固有 ID とは、それ自体は特定の個人を識別しないものの、エンタープライズ サービスをユーザーに提供するために使われるシステム生成番号です。 また、ユーザー名などの、特定を可能にするエンド ユーザーの情報がシステム生成データに含まれることもあります。 <br><br> **サポート データ**: オンライン サービスに関するテクニカル サポートを得るために、マイクロソフトとの契約に基づきマイクロソフトにお客様自身が提供するデータ、またはお客様の代わりに提供されるデータ (あるいはお客様がマイクロソフトに対し、オンライン サービスから取得を許可しているデータ) です。 <br><br> Windows 向けデータ プロセッサー サービスで処理されるデータの詳細については、「[オンライン サービスの使用条件](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46)」および [Microsoft トラスト センター](https://www.microsoft.com/trustcenter) を参照してください。 |
| データ保持 | マイクロソフトは、お客様がオンライン サービスを利用する権限を有している期間中、または OST の条件に基づきすべての顧客データが削除またはお客様により取得されるまで、顧客データを保存および処理します。 お客様のサブスクリプション期間中は常に、お客様は Windows 向けデータ プロセッサー サービスに格納されている顧客データをエクスポートできます。 お客様は、「[Windows 向けデータ プロセッサー サービスのデータ主体要求に関する GDPR ドキュメント](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)」で説明されている機能を使用して、データ主体要求に従い個人データを削除できます。
| 個人データの保存場所と移転 | Windows 向けデータ プロセッサー サービスの顧客のデータは、米国の Microsoft データ センターに存在します。 |
| 第三者とのデータの共有 | Microsoft shares data with third parties acting as our subprocessors (i.e., subcontractors which process personal data) to support functions such as customer and technical support, service maintenance, and other operations. Any subcontractors to which Microsoft transfers Customer Data or Support Data will have entered into written agreements with Microsoft that are no less protective than the Data Protection Terms of the [Online Services Terms](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). All third-party subcontractors with which Customer Data or Support Data is shared are included in the [Lists of subcontractors](https://www.microsoft.com/trustcenter/privacy/who-can-access-your-data-and-on-what-terms#subcontractors) (see “We limit access by subprocessors”). <br><br> Information regarding Microsoft’s response to law enforcement and third party requests for Customer Data and Support Data is located in the Online Services Terms. Unless Microsoft is legally prohibited from doing so, Microsoft will attempt to redirect the law enforcement agency or third party directly to the Customer. |
| データ主体の権利 | Microsoft は、処理者として活動するとき、お客様 (管理者) がそのデータ主体の個人データを利用できるようにし、GDPR に基づいて権利を行使するときデータ主体の要求を満たすことができるようにします。 Microsoft は、製品の機能およびデータ処理者としての役割と一貫性のある方法でこれを行います。Microsoft が、お客様のデータ主体から GDPR に基づき 1 つ以上の権利を行使する要求を受け取った場合、その要求をデータ管理者にリダイレクトします。 <br><br> 「[Windows 向けデータ プロセッサー サービスのデータ主体要求に関する GDPR ドキュメント](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)」では、Windows 向けデータ プロセッサー サービスの機能を使用してデータ主体の権利に対応する方法を説明しています。 |
| 目的に対する処理作業の必要性および比例性の評価 | このような評価は、データ管理者のニーズと処理の目的に応じて異なります。 <br><br> With regard to the processing carried out by Microsoft, such processing is necessary and proportional for the purpose of providing the services to the data controller. Microsoft makes this commitment in the OST. |
| データ主体の権利および自由に関するリスクの評価 | Windows 向けデータ プロセッサー サービスの使用に伴うデータ主体の権利および自由に関する主なリスクは、データ管理者が Windows 向けデータ プロセッサー サービスを実装、構成、使用する方法およびその文脈の影響を受けます。 <br><br> However, as with any service, personal data held in the service may be at risk of unauthorized access or inadvertent disclosure. Measures Microsoft takes to address such risks are discussed in the OST, as further detailed below. |
| リスクに対処するために予定された対策。データ主体および関連する他者の権利および正当な利益を考慮し、個人データの保護を確実にし、GDPR の遵守を証明するための保護措置、安全対策および安全メカニズムを含む。 | Microsoft is committed to helping protect the security of Customer Data. The security measures Microsoft takes are described in detail in the OST. <br><br> マイクロソフトは、処理する個人データを保護するために、適切な技術的対策および組織的対策を実施しています。 これらの対策には、社内プライバシー ポリシーとその実践、契約上の約束、国際標準および地域標準の認証などがありますが、これらに限られません。 詳細については、トラスト センターの[プライバシー基準に関するページ](https://www.microsoft.com/trustcenter/privacy/we-set-and-adhere-to-stringent-standards)を参照してください。  <br><br> Microsoft provides significant, transparent customer facing security and privacy materials to help explain Microsoft’s use and processing of personal data. Customers are encouraged to contact Microsoft with questions. <br><br> また、マイクロソフトはデータ処理者に適用されるその他のすべての GDPR の義務に準拠しています。これには、データ保護影響評価および記録管理の実施などが含まれます。| 
