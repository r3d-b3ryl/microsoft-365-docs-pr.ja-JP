---
title: プライバシーと個人データ
description: サービスによって収集、保存、および使用されるデータの詳細
keywords: GDPR、保持、削除、ストレージ、保持、処理、セキュリティ、監査
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3f1a251d98be5b3a9fefa5c1f6d5d5562516d5d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908176"
---
# <a name="privacy-and-personal-data"></a>プライバシーと個人データ

ユーザーは、Microsoft Managed Desktop が管理するデバイスでデータを受信、送信、および保存できます。 データのプライバシーが保護され、期待と一致する方法でのみ使用されるという信頼を得るのです。 この記事では、Microsoft Managed Desktop が個人データを収集、保存、保持、プロセス、セキュリティ保護、共有、監査、およびエクスポートする方法について説明します。 また、管理者が個人データを表示、修正、削除する方法も学習します。

Microsoft Managed Desktop は、プロファイリング、広告、またはマーケティングの目的でサービスを提供する一環として収集された個人データを使用しません。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft Managed Desktop のデータ収集

ユーザーが企業のデバイスを Microsoft Managed Desktop に登録すると、Windows と Microsoft Intune を使用して、データ収集がテクニカル 層で処理されます。 これらのソースは、Microsoft Managed Desktop のデバイス名など、ユーザーのデバイスに関する個人データを収集し、Microsoft Managed Desktop エクスペリエンスで管理および提供するデバイスを識別できます。

Microsoft Managed Desktop は、サービスを提供するためにそれ自体でデータを収集 [しません (IT 管理者の連絡先情報を除く](#it-admin-contact-information))。 代わりに、Microsoft Managed Desktop は、Windows や Microsoft Intune などの他のソースが既に収集したデータを再利用します。 Microsoft Managed Desktop では、これらのサービスが登録済みデバイスから収集するデータを使用します。

- Microsoft Managed Desktop によって管理されるデバイスからの Windows 診断データは、Microsoft の Windows 診断データ ストアに送信されます。
- Microsoft Managed Desktop では、 [登録済みデバイスの](/learn/modules/introduction-to-modern-management-in-microsoft-365/) 管理にモダン管理を使用します。 "モダン管理" の一環として、デバイスをテナントの Azure Active Directory に登録する必要があります。
- 高度に最適化された安全な構成を登録済みデバイスに配布するために、Microsoft Managed Desktop は Microsoft Intune を使用します。
- Microsoft Managed Desktop は、Microsoft Defender Advanced Thread Protection のセキュリティ インテリジェンス データを、そのサービスを使用する顧客に使用します。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop のデータ ストレージとソース

Microsoft Managed Desktop がデータを取得した後、そのデータのサービス、ストレージ、および処理を提供する必要があります。

### <a name="storing-data-storage-location-and-data-retention"></a>データ、保存場所、およびデータ保持の保存

Microsoft Managed Desktop は、次の Microsoft ストレージ サービスの 1 つ以上にデータを格納します。

- Azure SQL
- Azure ストレージ
- Dynamics 365

Microsoft Managed Desktop は、そのデータを米国に保存します。 個人データは、Microsoft Defender for Endpoint によって収集された Microsoft Managed Desktop デバイスのアラート データを除き、最大 30 日間、Microsoft Managed Desktop によって保持されます。 実際のアラート データ (個人データを含む可能性があります) は 180 日間保存されます。 個人データが削除されたアラート データは、最大 2 年間保存されます。 Microsoft Managed Desktop は、一般データ保護規則 (GDPR) およびカリフォルニア州消費者プライバシー法 (CCPA) に準拠して、アラート データに格納されている個人データに対するデータ主体の権利を尊重します。

### <a name="staff-location"></a>スタッフの場所

Microsoft Managed Desktop Operations および Security Operations チームは、米国とインドに位置しています。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft Managed Desktop のデータ使用量

Microsoft Managed Desktop では、次のデータを使用します。


| データ ソース |Microsoft Managed Desktop での使用  |
|---------|---------|
|Azure Active Directory データ     | Microsoft Managed Desktop Admin ポータルで使用できるテナント管理者用に作成されたレポートで使用されます。        |
|Intune データ     | Microsoft Managed Desktop Admin ポータルで使用できるテナント管理者用に作成されたレポートで使用されます。        |
|Microsoft Defender for Endpoint     |  Microsoft Managed Desktop のセキュリティ 操作センター (SOC) によって登録されたデバイスで検出されたセキュリティの脅威に対処するために使用されます。  |
|Windows 診断データ     |管理対象デバイスの更新状態を判断し、Microsoft Managed Desktop の IT-as-a-Service (ITaaS) サービスを提供および改善するために使用されます。         |
|管理者連絡先データ     | Microsoft Managed Desktop がテナント管理者と通信するために使用します。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop によって処理されるエンティティ

Microsoft Managed Desktop は、サービスを提供するためにこれらのエンティティを処理します。

- デバイス データ
- デバイス セキュリティ設定
- デバイス オペレーティング システムとハードウェア
- デバイスの正常性に関する集約された情報
- デバイス診断情報
- テナント データ
- Azure Active Directory リソース
- ポリシーと構成データ
- Microsoft Defender for Endpoint メタデータとアラート データ
- Windows 診断データ
- 製品とサービスの使用状況データ

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft Managed Desktop で使用される ID データは、組織が Office 365 や Azure などの Microsoft オンライン サービスを購読するときに提供されるアドレスに基づいて、地理的な場所に Azure Active Directory によって格納されます。 Azure Active Directory のデータセンターを示すマップについては [、「Microsoft Azure-](http://azuredatacentermap.azurewebsites.net/) お客様データはどこにあるか」を参照してください。

Azure がデータ ストレージに使用する地域の詳細については [、「Azure Active Directory-データの場所」を参照してください](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune データは、ヨーロッパ北 (アイルランド) やヨーロッパ西部 (オランダ) など、いくつかの異なる地域に格納できます。 IT 管理者がテナント アカウントを作成し、Intune サービスに最初に登録するときにデータが保存される国を選択します。 Intune で使用されるデータセンターの場所の一覧については [、「Microsoft Intune-お客様のデータはどこにあるか」を参照してください](http://intunedatacentermap.azurewebsites.net/)。 Intune によるデータストレージと使用の詳細については、「Intune での [データ収集」を参照してください](/intune/privacy-data-collect)。

### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

Microsoft Defender for Endpoint データは、いくつかの異なる地域に格納できます。 このため、Defender for Endpoint は、Microsoft [Defender for](http://intunedatacentermap.azurewebsites.net/)Endpoint- Data storage locations で述べたように、欧州連合、英国、および米国の Microsoft Azure データセンターで動作します。 Defender for Endpoint によるデータストレージと使用の詳細については、「Microsoft Defender for Endpoint が収集する [データとは」を参照してください。](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

Microsoft プライバシーに関する声明に記載されている通り [、「Microsoft](https://privacy.microsoft.com/privacystatement)が収集した個人データは、お客様の地域、米国、および Microsoft その関連会社、子会社、またはサービス プロバイダーが施設を運営する他の国に保存および処理される場合があります。 [...]通常、プライマリ ストレージの場所は、顧客の地域または米国内で、多くの場合、別の地域のデータセンターへのバックアップを使用します。 記憶域の場所は、効率的に動作し、パフォーマンスを向上させるために、および障害や他の問題が発生した場合にデータを保護するために冗長性を作成するために選択されます。 このプライバシーに関する声明に基いて収集したデータが、この声明の規定と、データがどこに置かれる場合でも適用される法律の要件に従って処理されるのを確認するための手順を実行します。

Windows 10 の診断データ収集の詳細については、「Microsoft [](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) Privacy Statement」の「個人データの保存と処理」セクションを参照してください。

## <a name="data-access-protection"></a>データ アクセス保護

Microsoft Managed Desktop の内部データ ストアへの直接アクセスは、いくつかの方法で制限されています。

- エンジニアリング リード レベルの承認が必要です。
- 監査と時間制限の両方です。
- 高度にセキュリティで保護された制限付きワークステーションを使用する必要があります。
- すべてのデータは、保存中に暗号化されます。
- 立ち上がりアクセスはありません。
- Microsoft Managed Desktop の内部管理ポータルへのアクセスには、高度にセキュリティで保護された制限付きワークステーションが必要です。

## <a name="processing-personal-data-in-a-compliant-manner"></a>準拠した方法で個人データを処理する
Microsoft Managed Desktop は、ISO 認定システムを使用して個人データを処理します。 詳細については、「コンプライアンス」を [参照してください](../intro/compliance.md)。

## <a name="profiling-and-marketing"></a>プロファイリングとマーケティング

Microsoft Managed Desktop は、プロファイリング、広告、またはマーケティングの目的でサービスを提供する一環として収集された個人データを使用しません。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のためのデータ対象要求

EU 一般データ保護規則 [(GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、雇用主または他の種類の機関または組織 (データ 管理者または単なる管理者と呼ばれる) によって収集された個人データを管理する権限をユーザー (データ主体として知られている) に与えます。 GDPR での個人データは、特定されたまたは特定可能な自然人に関連するすべてのデータと、非常に幅広く定義されています。 GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの修正の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。 データ主体がコントローラーに対して個人データへのアクションを実行するよう正式に要求することを、データ主体の要求または DSR と呼びます。

同様に、CCPA は、GDPR のデータ主体の権利に類似する権利 (個人情報の削除、アクセス、および受信 (移植性) などの権利を含む、カリフォルニア州の消費者にプライバシー権と義務を提供します。 また、CCPA は、特定の開示、行使権を選択する際の差別に対する保護、および"販売" に分類される特定のデータ転送に対する"オプトアウト/オプトイン" 要件も提供します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](/compliance/regulatory/offering-ccpa?view=o365-worldwide)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](/compliance/regulatory/ccpa-faq?view=o365-worldwide)」を参照してください。

次のセクションでは、Microsoft Managed Desktop が使用する個人データまたは個人情報を見つけ、アクセスし、処理するために、管理者が Microsoft Managed Desktop を支援する方法について説明します。

> [!NOTE]
> GDPR に関する一般的な情報を探している場合は、サービス信頼ポータルの [GDPR](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) セクションを参照してください。

### <a name="it-admin-contact-information"></a>IT 管理者の連絡先情報

テナント管理者は、Microsoft 管理デスクトップ ポータルの [管理者連絡先] セクションで、自分の個人データ (自分の連絡先情報など) を直接表示、修正、削除できます。

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Microsoft Defender for Endpoint アラート データ

セキュリティ管理者は、環境内の Microsoft Managed Desktop 管理対象デバイスで、Microsoft Defender for Endpoint アラートに関連する個人データの抽出または削除を要求できます。 セキュリティ管理者は、Microsoft Managed Desktop [Admin Portal](https://aka.ms/memadmin) にサインインし、サポート要求を送信する必要があります。 [**変更要求] 、[** セキュリティのカテゴリ] 、および [その他のサブカテゴリ] の [サポート要求の種類] を選択し、データの抽出または削除の要求と共に、説明に関連するデバイス名を指定します。  

### <a name="user-related-personal-data"></a>ユーザー関連の個人データ

これとは別に、Microsoft Managed Desktop は個人データを独自に収集しない。 代わりに、他の Microsoft Enterprise Online Services が収集した個人データに依存して使用します。 個人データの表示、修正、削除を求め、ユーザーの要求に対応する IT 管理者は、Microsoft Managed Desktop が依存する基になるサービスのそれぞれの機能を使用できます。 これらのサービスで使用される個人データを表示または削除する場合は、 [最初に「GDPR の Azure Data Subject Requests」を参照](/compliance/regulatory/gdpr-dsr-Azure) してください。

さらに、Microsoft Managed Desktop が個人データの収集に依存するサービスの DSRs を実行するには、次のガイダンスを使用します。

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [エンドポイント用 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)