---
title: Microsoft の microsoft Information Protection (365)
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 コンプライアンスを使用して Microsoft Information Protection (MIP) 機能を実装することで、機密情報がどこに存在している場合でも機密情報を検出、分類、保護することができます。
ms.openlocfilehash: d69395523cb656d23e44b577f01338eb78c7b386
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277524"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft の microsoft Information Protection (365)

>*[Microsoft 365 セキュリティ & コンプライアンスのライセンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Microsoft Information Protection (MIP) を使用して、機密性の高い情報をどこにいても、どこからでも検出、分類、保護することができます。

MIP 機能は、Microsoft 365 コンプライアンスに含まれており、 [データを把握](#know-your-data)し、データを [保護](#protect-your-data)し、 [データ損失を防止](#prevent-data-loss)するためのツールを提供します。

![データを把握し、データを保護し、データの損失を防ぎ、データを管理する](../media/powered-by-intelligent-platform.png)

データの管理の詳細については、microsoft [365 の Microsoft Information ガバナンス](manage-Information-governance.md)を参照してください。

## <a name="know-your-data"></a>データを把握する

データの状況を理解し、ハイブリッド環境全体で重要なデータを識別するには、次の機能を使用します。
 
|機能|どのような問題が解決されますか。|作業の開始|
|:------|:------------|:--------------------|:-----------------------------|
|[機密情報の種類](sensitive-information-type-entity-definitions.md)| 組み込みまたはカスタムの正規表現または関数を使用して機密データを識別し、補強エビデンスと共にキーワード、信頼度、および近接性を含むものを指定します。| [組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)|
|[Trainable 分類子 (プレビュー)](classifier-learn-about.md)| 組み込み分類子の1つを使用して、または独自のコンテンツで分類子をトレーニングすることで、データを分類します。 | [トレーニング可能な分類子の使用を開始する (プレビュー)](classifier-get-started-with.md) |
|[データ分類](data-classification-overview.md) | 機密ラベル、保持ラベル、または組織内の機密情報の種類として分類されているアイテムと、ユーザーがそのアイテムに対して行った操作を識別します。  | [コンテンツ エクスプローラーの使用を開始する](data-classification-content-explorer.md)<br /><br /> [アクティビティ エクスプローラーの使用を開始する](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>データを保護する

暗号化、アクセス制限、および視覚マークを含む柔軟な保護アクションを適用するには、次の機能を使用します。

|機能|どのような問題が解決されますか。|作業の開始|
|:------|:------------|---------------------|:----------------------------|
|[機密ラベル](sensitivity-labels.md)| アプリケーション、サービス、およびデバイスにまたがる単一のソリューション。データをラベル付けして、組織の内外で転送する際にデータを保護します。 <br /><br />シナリオ例: [POWER BI で機密ラベルを適用および表示し、エクスポート時にデータを保護する](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|[ 機密ラベルの概要](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Windows コンピューターの場合は、すべてのファイルの種類のラベル付けと保護をファイルエクスプローラーと PowerShell から行うことができる追加の機能の機密ラベルを拡張します。<br /><br /> その他の機能 [の例: Azure Information Protection の統合されたラベル付けクライアントのカスタム構成](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 統合されたラベル付けされたクライアント管理者ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[二重キー暗号化](double-key-encryption.md)| すべての状況において、保護されたコンテンツを復号化するか、または規制要件に応じて、暗号化キーを地理的な境界内に保持する必要があります。 | [二重キー暗号化の展開](double-key-encryption.md)|
|[Office 365 メッセージの暗号化](ome.md) (OME)| 任意のデバイスで任意のユーザーに送信される電子メールメッセージと添付ドキュメントを暗号化します。これにより、承認済みの受信者のみがメールの情報を読むことができます。  <br /><br />シナリオ例: [高度なメッセージ暗号化によって暗号化された電子メールを取り消す](revoke-ome-encrypted-mail.md) | [Office 365 のメッセージの暗号化を開始する](set-up-new-message-encryption-capabilities.md)|
|[カスタマー キーによるサービスの暗号化](customer-key-overview.md) | 許可されていないシステムまたは個人によるデータの表示を防止し、Microsoft データセンターの BitLocker ディスク暗号化を補完します。 | [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|ユーザーがドキュメントをチェックアウトするときに、ダウンロードしたファイルが保護されるように、指定したポリシーに従って、承認されたユーザーのみがファイルを表示して使用できるようにします。 | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Rights Management コネクタ](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Exchange または SharePoint Server を使用する既存のオンプレミスの展開、または Windows Server とファイル分類インフラストラクチャ (FCI) を実行するファイルサーバーに対してのみ保護を行う | [RMS コネクタを展開する手順](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection の統合されたラベル付けスキャナー](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| オンプレミスのデータストアに存在する機密情報を検出、ラベル付け、保護します。 | [Azure Information Protection の統合ラベル付けされたスキャナーを構成およびインストールする](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| クラウド内のデータストアに存在する機密情報を検出、ラベル付け、保護する | [クラウドに保存されている規制対象および機密データを検出、分類、ラベル付け、保護する](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 情報保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|サードパーティ製のアプリおよびサービスに対して機密ラベルを拡張します。  <br /><br /> シナリオ例: [機密ラベルを設定および取得する (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft Information Protection (MIP) SDK のセットアップと構成](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>データの損失を防止する

機密情報の偶発的な共有を防止するために、次の機能を使用します。


|機能|どのような問題が解決されますか。|作業の開始|
|:------|:------------|:---------------------|:-----------------------------|
|[データ損失防止](data-loss-prevention-policies.md) (DLP)| 機密アイテムの意図しない共有の防止に役立てる <br /><br />シナリオ例: [Microsoft Teams の機密情報をチャットおよびチャネルメッセージで保護](dlp-microsoft-teams.md)する | [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)|
|[エンドポイントのデータ損失防止 (プレビュー)](endpoint-dlp-learn-about.md)| Windows 10 コンピューターで使用および共有されるアイテムに DLP 機能を拡張します。 | [エンドポイント データ損失防止(プレビュー) を開始する](endpoint-dlp-getting-started.md)|
