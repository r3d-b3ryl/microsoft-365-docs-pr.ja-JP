---
title: プライバシーおよび個人データ
description: サービスで収集、格納、および使用されるデータの詳細
keywords: GDPR、保持、削除、保存、保存、処理、セキュリティ、監査
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: e1b0c856a3bfb886521ee2c1a2115e4c29504862
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47363262"
---
# <a name="privacy-and-personal-data"></a>プライバシーおよび個人データ

ユーザーは、Microsoft マネージドデスクトップで管理されているデバイスでデータの受信、送信、保存を行うことができます。 これらは、データのプライバシーが保護され、期待に沿った方法でのみ使用されることを信頼しています。 この記事では、Microsoft の管理されたデスクトップが個人データの収集、保存、保持、処理、保護、共有、監査、およびエクスポートを行う方法について説明します。 また、管理者が個人データを表示、修正、および削除する方法についても説明します。

Microsoft マネージドデスクトップでは、プロファイル、広告、またはマーケティングの目的で収集された個人データを、サービス提供の一環として使用していません。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのデータ収集

ユーザーが会社のデバイスを Microsoft マネージドデスクトップに登録する場合は、Windows と Microsoft Intune を使用して、技術層でデータ収集を処理します。 これらのソースは、Microsoft マネージドデスクトップのデバイス名など、ユーザーのデバイスに関する個人データを収集して、管理対象のデバイスを識別し、Microsoft マネージドデスクトップエクスペリエンスを提供します。

Microsoft マネージドデスクトップでは、サービスを提供するために単独でデータが収集されることはありません ( [IT 管理者の連絡先情報](#it-admin-contact-information)を除く)。 代わりに、Microsoft Managed Desktop は、Windows や Microsoft Intune などの他のソースが既に収集したデータを再利用します。 Microsoft マネージドデスクトップは、登録されたデバイスから収集したサービスのデータを使用します。

- Microsoft マネージドデスクトップで管理されているデバイスからの windows 診断データは、Microsoft の Windows 診断データストアに送信されます。
- Microsoft マネージドデスクトップは、登録済みデバイスを管理するために [モダン管理](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) を使用します。 その一環として、デバイスはテナントの Azure Active Directory に登録されている必要があります。
- 高度に最適化された安全な構成を登録済みデバイスに配布するために、Microsoft Managed Desktop は Microsoft Intune を使用します。
- Microsoft Managed Desktop は、Microsoft Defender Advanced Thread Protection から、そのサービスを使用するお客様にセキュリティインテリジェンスデータを使用します。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのデータストレージとソース

Microsoft マネージドデスクトップはデータを取得した後、そのデータのサービス、ストレージ、および処理を提供するために、次のように処理を行う必要があります。

### <a name="storing-data-storage-location-and-data-retention"></a>データ、保存場所、データ保持の格納

Microsoft マネージドデスクトップは、次の Microsoft ストレージサービスの1つ以上にデータを格納します。

- Azure SQL
- Azure ストレージ

Microsoft マネージドデスクトップは、そのデータを米国に格納します。 個人データは、Microsoft 管理デスクトップによって最大30日間保持されます。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップのデータ使用率

Microsoft マネージドデスクトップでは、次のデータが使用されます。


| データ ソース |Microsoft マネージドデスクトップで使用する  |
|---------|---------|
|Azure Active Directory データ     | テナント管理者用に作成されたレポートで使用されます。これは、Microsoft Managed Desktop 管理ポータルで利用できます。        |
|Intune データ     | テナント管理者用に作成されたレポートで使用されます。これは、Microsoft Managed Desktop 管理ポータルで利用できます。        |
|Microsoft Defender Advanced Threat Protection (ATP)     |  Microsoft マネージドデスクトップのセキュリティ操作センター (SOC) によって検出されたセキュリティ上の脅威に対処するために使用します。  |
|Windows 診断データ     |管理対象デバイスの更新状況を判断したり、Microsoft Managed Desktop's a Service (ITaaS) オファーリングを提供および改善したりするために使用されます。         |
|管理者の連絡先データ     | テナント管理者と通信するために Microsoft マネージドデスクトップによって使用されます。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップによって処理されたエンティティ

Microsoft マネージドデスクトップは、次のエンティティを処理してサービスを提供します。

- デバイスデータ
- デバイス セキュリティ設定
- デバイスのオペレーティングシステムとハードウェア
- デバイスの正常性に関する集計情報
- デバイスの診断情報
- テナントデータ
- Azure Active Directory のリソース
- ポリシーおよび構成データ
- Microsoft Defender ATP のメタデータ
- Windows 診断データ
- 製品およびサービスの利用状況データ

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft マネージドデスクトップによって使用される id データは、Office 365 または Azure などの Microsoft online services をサブスクライブする際に組織によって指定されたアドレスに基づいて、Azure Active Directory によって地理的な場所に格納されます。 Azure Active Directory のデータセンターを示すマップについては、「 [Microsoft azure-顧客データの場所](http://azuredatacentermap.azurewebsites.net/) 」を参照してください。

Azure がデータ記憶域に使用する地域の詳細については、「 [Azure Active Directory-データの場所](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)」を参照してください。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune データは、ヨーロッパ北部 (アイルランド) やヨーロッパ西部 (オランダ) など、いくつかの異なる地域に格納できます。 IT 管理者は、テナントアカウントを作成し、Intune サービスに最初に登録するときにデータを格納する国を選択します。 Intune で使用されるデータセンターの場所の一覧については、「 [Microsoft intune-お客様のデータはどこ](http://intunedatacentermap.azurewebsites.net/)にありますか?」を参照してください。 データストレージの詳細と Intune での使用の詳細については、「 [intune でのデータ収集](https://docs.microsoft.com/intune/privacy-data-collect)」を参照してください。

### <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection

Microsoft Defender Advanced Threat Protection (ATP) のデータは、いくつかの異なる地域に格納できます。 このため、microsoft Defender ATP は、microsoft [DEFENDER atp](http://intunedatacentermap.azurewebsites.net/)に記載されているように、欧州連合、英国、および米国の microsoft Azure データセンターで運用されます。 データストレージの詳細と Microsoft Defender ATP での使用方法については、「 [Microsoft DEFENDER atp が収集するデータ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)」を参照してください。

### <a name="windows-10"></a>Windows 10

「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」に記載されているように、「microsoft が収集した個人データは、お客様の地域、米国、および microsoft またはその関連会社、子会社、またはサービスプロバイダーが施設で運用している他の国での保存と処理が可能です。 [...]通常、プライマリストレージの場所は、お客様の地域または米国にあり、別の地域のデータセンターへのバックアップが含まれている場合があります。 ストレージの場所は、パフォーマンスを向上させるために、また、停止やその他の問題が発生した場合にデータを保護するために冗長性を作成するために選択されます。 このプライバシーに関する声明で収集したデータが、この声明の条項と、データが配置されている場合の適用法の要件に従って処理されるようにするための手順を実行します。

Windows 10 の診断データコレクションの詳細については、「Microsoft のプライバシーに関する声明」の [「個人データを保存して処理](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) する」を参照してください。

## <a name="data-access-protection"></a>データアクセス保護

Microsoft マネージデスクトップの内部データストアへの直接アクセスは、いくつかの方法で制限されています。

- エンジニアリングのリードレベルの承認が必要です。
- 監査と時間制限の両方です。
- セキュリティで保護された、制限の厳しいワークステーションを使用する必要があります。
- すべてのデータは、保存されている間は暗号化されます。
- 永続的なアクセスはありません。
- Microsoft Managed Desktop の内部管理ポータルにアクセスするには、高度にセキュリティ保護され、制限されたワークステーションが必要です。

## <a name="processing-personal-data-in-a-compliant-manner"></a>コンプライアンスに準拠した方法で個人データを処理する
Microsoft マネージドデスクトップは、ISO 認定システムで個人データを処理します。 詳細については、「 [コンプライアンス](../intro/compliance.md)」を参照してください。

## <a name="profiling-and-marketing"></a>プロファイルとマーケティング

Microsoft マネージドデスクトップでは、プロファイル、広告、またはマーケティングの目的で収集された個人データを、サービス提供の一環として使用していません。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR と CCPA のためのデータ主体の要求

欧州連合の [一般的なデータ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、雇用者またはその他の種類の代理人または組織 (データコントローラーまたはコントローラーとも呼ばれる) によって収集された個人データを管理するために、ユーザーに対して (「データのサブジェクト」としての規則に従って) 権限を与えます。 GDPR での個人データは、特定されたまたは特定可能な自然人に関連するすべてのデータと、非常に幅広く定義されています。 GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの修正の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。 データ主体がコントローラーに対して個人データへのアクションを実行するよう正式に要求することを、データ主体の要求または DSR と呼びます。

同様に、カリフォルニアコンシューマ Privacy Act (CCPA) は、GDPR のデータ主体の権利に似た、個人情報の削除、アクセス、受信 (移植性) などの権限を含む、カリフォルニアのコンシューマーに対してプライバシー権限と義務を提供します。 CCPA は、特定の開示、ようエクササイズ権限の場合の差別に対する保護、および「sales」として分類される特定のデータ転送の「オプトアウト/オプトイン」要件も提供します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)」を参照してください。

次のセクションでは、Microsoft マネージドデスクトップが、Microsoft マネージドデスクトップによって使用される個人データや個人情報の検索、アクセス、および操作をどのようにサポートしているかについて説明します。

> [!NOTE]
> GDPR に関する一般的な情報については、「Service Trust Portal の [GDPR」セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) を参照してください。

### <a name="it-admin-contact-information"></a>IT 管理者の連絡先情報

テナント管理者は、Microsoft マネージドデスクトップポータルの [管理者の連絡先] セクションで、自分の個人データを直接表示、修正、および削除できます。

### <a name="user-related-personal-data"></a>ユーザーに関連する個人データ

これに加えて、Microsoft マネージドデスクトップでは、個人データは自分では収集されません。 その代わりに、他の Microsoft Enterprise Online サービスが収集した個人データを利用して使用します。 個人データを表示、修正、および削除するためのユーザー要求に応答することを望んでいる IT 管理者は、Microsoft Managed Desktop が依存する基礎となるサービスのそれぞれの機能を使用できます。 これらのサービスによって使用される個人データの表示または削除については、最初に [GDPR 記事の Azure データ主体要求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) を参照してください。

さらに、次のガイダンスを使用して、Microsoft Managed Desktop のサービスに対して DSRs を実行することによって、個人データのコレクションが異なります。

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender ATP](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
