---
title: プライバシーと個人データ
description: サービスによって収集、保存、使用されるデータの詳細
keywords: GDPR, 保持, 削除, ストレージ, 保持, 処理, セキュリティ, 監査
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7005e09d5a3df158569e132d2954f3b9a0ebf371
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840483"
---
# <a name="privacy-and-personal-data"></a>プライバシーと個人データ

ユーザーは、Microsoft マネージド デスクトップで管理されているデバイスでデータを受信、送信、および保存できます。 ユーザーは、データのプライバシーが保護され、期待と一致する方法でのみ使用されるという信頼を持っています。 この記事では、Microsoft マネージド デスクトップが個人データを収集、保存、保持、処理、セキュリティ保護、共有、監査、およびエクスポートする方法について説明します。 また、管理者が個人データを表示、修正、および削除する方法も学習します。

Microsoft マネージド デスクトップは、プロファイリング、広告、またはマーケティングの目的でサービスを提供する一環として収集された個人データを使用しません。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのデータ収集

ユーザーが企業のデバイスを Microsoft マネージド デスクトップに登録すると、Windows と Microsoft Intune を使用してデータ収集が技術層で処理されます。 これらのソースは、Microsoft マネージド デスクトップのデバイス名など、ユーザーのデバイスに関する個人データを収集して、Microsoft マネージド デスクトップ エクスペリエンスで管理および提供されるデバイスを識別できます。

Microsoft マネージド デスクトップは、サービスを提供するためにそれ自体でデータを [収集しません (IT 管理者の連絡先情報を除く](#it-admin-contact-information))。 代わりに、Microsoft マネージド デスクトップは、Windows や Microsoft Intune などの他のソースが既に収集したデータを再利用します。 Microsoft マネージド デスクトップでは、これらのサービスが登録済みデバイスから収集するデータを使用します。

- Microsoft マネージド デスクトップで管理されているデバイスからの Windows 診断データは、Microsoft の Windows 診断データ ストアに送信されます。
- Microsoft マネージド デスクトップでは、 [登録済みデバイスの](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) 管理に最新の管理を使用します。 "最新の管理" の一部として、デバイスはテナントの Azure Active Directory に登録する必要があります。
- 高度に最適化され、セキュリティ保護された構成を登録済みデバイスに配布するために、Microsoft マネージド デスクトップでは Microsoft Intune を使用します。
- Microsoft マネージド デスクトップは、Microsoft Defender Advanced Thread Protection のセキュリティ インテリジェンス データを、そのサービスを使用するユーザーに使用します。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのデータ ストレージとソース

Microsoft マネージド デスクトップは、データを取得した後、そのデータのサービス、ストレージ、および処理を次のように提供する必要があります。

### <a name="storing-data-storage-location-and-data-retention"></a>データ、保存場所、およびデータ保持の保存

Microsoft マネージド デスクトップは、次の Microsoft ストレージ サービスの 1 つ以上にデータを格納します。

- Azure SQL
- Azure Storage

Microsoft マネージド デスクトップは、そのデータを米国に保存します。 個人データは、Microsoft マネージド デスクトップによって最大 30 日間保持されます。

### <a name="staff-location"></a>スタッフの場所

MMD 運用チームと MMD セキュリティ運用チームは、米国およびインドに位置しています。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップのデータ使用状況

Microsoft マネージド デスクトップでは、次のデータを使用します。


| データ ソース |Microsoft マネージド デスクトップで使用する  |
|---------|---------|
|Azure Active Directory データ     | テナント管理者用に作成されたレポートで使用されます。このレポートは、Microsoft Managed Desktop Admin ポータルで利用できます。        |
|Intune データ     | テナント管理者用に作成されたレポートで使用されます。これは、Microsoft Managed Desktop Admin ポータルで利用できます。        |
|Microsoft Defender for Endpoint     |  Microsoft マネージド デスクトップのセキュリティ オペレーション センター (SOC) によって登録済みデバイスで検出されたセキュリティの脅威に対処するために使用されます。  |
|Windows 診断データ     |管理対象デバイスの更新状態を判断し、Microsoft マネージド デスクトップのサービスとしての IT (ITaaS) サービスを提供および改善するために使用されます。         |
|管理者の連絡先データ     | テナント管理者と通信するために Microsoft マネージド デスクトップで使用されます。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップによって処理されるエンティティ

Microsoft マネージド デスクトップは、これらのエンティティを処理してサービスを提供します。

- デバイス データ
- デバイス セキュリティ設定
- デバイスのオペレーティング システムとハードウェア
- デバイスの正常性に関する集計情報
- デバイス診断情報
- テナント データ
- Azure Active Directory リソース
- ポリシーと構成データ
- Microsoft Defender for Endpoint メタデータ
- Windows 診断データ
- 製品とサービスの利用状況データ

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft マネージド デスクトップで使用される ID データは、組織が Office 365 や Azure などの Microsoft オンライン サービスをサブスクライブするときに提供されるアドレスに基づいて、地理的な場所に Azure Active Directory によって保存されます。 Azure Active Directory のデータセンターを示すマップについては [、Microsoft Azure](http://azuredatacentermap.azurewebsites.net/) の「顧客データの場所」をご覧ください。

Azure がデータ ストレージに使用する地域の詳細については [、「Azure Active Directory–データの場所」を参照してください](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune データは、ヨーロッパ北 (アイルランド) やヨーロッパ西 (オランダ) など、いくつかの異なる地域に保存できます。 IT 管理者がテナント アカウントを作成し、データが Intune サービスに最初に登録するときにデータが保存される国を選択します。 Intune で使用されるデータセンターの場所の一覧については [、「Microsoft Intune—顧客](http://intunedatacentermap.azurewebsites.net/)データの場所」を参照してください。 Intune によるデータ ストレージと使用の詳細については、「Intune での [データ収集」を参照してください](https://docs.microsoft.com/intune/privacy-data-collect)。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Microsoft Defender for Endpoint データは、いくつかの異なる地域に保存できます。 このため、Defender for Endpoint は、データ ストレージの場所である [Microsoft Defender for Endpoint](http://intunedatacentermap.azurewebsites.net/)に記載されている通り、欧州連合、英国、および米国の Microsoft Azure データセンターで動作します。 Defender for Endpoint によるデータ ストレージと使用について詳しくは、「Microsoft Defender for Endpoint で収集される [データ」をご覧ください。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Microsoft のプライバシーに関する声明に記載されている「Microsoft によって収集された個人データは、お客様の地域、米国内、および [Microsoft](https://privacy.microsoft.com/privacystatement)または関連会社、子会社、またはサービス プロバイダーが施設を運営するその他の国に保存および処理される場合があります。 [...]通常、プライマリストレージの場所は、お客様の地域または米国内で、多くの場合、別の地域のデータセンターにバックアップされます。 記憶域の場所は、効率的に動作し、パフォーマンスを向上し、機能停止や他の問題が発生した場合にデータを保護するための冗長性を作成するために選択されます。 このプライバシーに関する声明の下で収集したデータが、この声明の規定およびデータが保存されている場所で適用される法律の要件に従って処理されるのを確認するための手順を実行します。"

Windows 10 の診断データの収集について詳しくは、Microsoft[](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)のプライバシーに関する声明の「個人データを保存および処理する場所」セクションをご覧ください。

## <a name="data-access-protection"></a>データ アクセス保護

Microsoft マネージド デスクトップの内部データ ストアへの直接アクセスは、いくつかの方法で制限されています。

- エンジニアリング リード レベルの承認が必要です。
- 監査と時間制限の両方です。
- セキュリティが高く制限されたワークステーションを使用する必要があります。
- 保存中は、すべてのデータが暗号化されます。
- 永続的なアクセスはありません。
- Microsoft マネージド デスクトップの内部管理ポータルにアクセスするには、セキュリティが高く制限されたワークステーションが必要です。

## <a name="processing-personal-data-in-a-compliant-manner"></a>準拠した方法で個人データを処理する
Microsoft マネージド デスクトップは、ISO 認定システムを使用して個人データを処理します。 詳細については、「コンプライアンス」を [参照してください](../intro/compliance.md)。

## <a name="profiling-and-marketing"></a>プロファイリングとマーケティング

Microsoft マネージド デスクトップは、プロファイリング、広告、またはマーケティングの目的でサービスを提供する一環として収集された個人データを使用しません。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のためのデータ対象要求

欧州連合一般データ保護規則 [(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、雇用主や他の種類の機関または組織 (データ管理者または単なるコントローラーと呼ばれる) によって収集された個人データを管理する権利を、個人 (この規則ではデータ主体と呼ばれる) に与えます。 GDPR での個人データは、特定されたまたは特定可能な自然人に関連するすべてのデータと、非常に幅広く定義されています。 GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの修正の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。 データ主体がコントローラーに対して個人データへのアクションを実行するよう正式に要求することを、データ主体の要求または DSR と呼びます。

同様に、カリフォルニア州消費者プライバシー法 (CCPA) は、個人情報を削除、アクセス、受信 (移植性) する権利など、GDPR のデータ主体の権利と同様の権利を含む、カリフォルニア州の消費者にプライバシーの権利と義務を提供します。 CCPA は、特定の開示、権利行使を選択する際の侵害に対する保護、および "販売" として分類される特定のデータ転送に対する「オプトアウト/オプトイン」要件も提供します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)」を参照してください。

次のセクションでは、管理者が Microsoft マネージド デスクトップで使用される個人データまたは個人情報の検索、アクセス、および処理を Microsoft マネージド デスクトップでどのように支援するかについて説明します。

> [!NOTE]
> GDPR に関する一般的な情報を探している場合は、Service Trust Portal の [GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) セクションを参照してください。

### <a name="it-admin-contact-information"></a>IT 管理者の連絡先情報

テナント管理者は、Microsoft マネージド デスクトップ ポータルの [管理者連絡先] セクションで、自分の個人データ (自分の連絡先情報など) を直接表示、修正、削除できます。

### <a name="user-related-personal-data"></a>ユーザー関連の個人データ

これとは別に、Microsoft マネージド デスクトップは、それ自身で個人データを収集するのではありません。 代わりに、他の Microsoft Enterprise Online Services が収集した個人データに依存して使用します。 ユーザーからの個人データの表示、修正、削除の要求に応える IT 管理者は、Microsoft マネージド デスクトップが依存している基になるサービスのそれぞれの機能を使用できます。 これらのサービスで使用される個人データを表示または削除する場合は、最初に [GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) 記事の Azure データ主体要求を参照してください。

さらに、次のガイダンスを使用して、Microsoft マネージド デスクトップが個人データの収集に依存するサービスの DSRs を実行します。

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender for Endpoint](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
