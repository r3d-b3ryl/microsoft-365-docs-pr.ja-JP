---
title: Microsoft 365 での Microsoft Information Protection
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
description: Microsoft 365 コンプライアンスを使用して Microsoft Information Protection (MIP) の機能を実装することで、機密情報が存在する場所や移動する場所をは検出、分類、保護できます。
ms.openlocfilehash: 96082bc70b093e763be00c847bb6a68ce302c8a9
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815206"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365 での Microsoft Information Protection

>*[Microsoft 365 セキュリティ センター コンプライアンス&ライセンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Microsoft Information Protection (MIP) を使用すると、機密情報が存在する場所や移動する場所を含む場所を保護するために役立ちます。

MIP 機能は Microsoft 365 コンプライアンスに含まれており、お使いのデータ [の把](#know-your-data)握、データ [の保護](#protect-your-data)、およびデータ損失防止を [行うツールが提供されます](#prevent-data-loss)。

![データの把握、データの保護、データ損失の防止、データの管理](../media/powered-by-intelligent-platform.png)

データの管理については [、Microsoft 365 の「Microsoft Information Governance」を参照してください](manage-Information-governance.md)。

## <a name="know-your-data"></a>データを把握する

ハイブリッド環境全体にわたってデータの横にわたり、重要なデータを特定するには、次の機能を使用します。
 
|機能|どのような問題が解決しますか。|概要|
|:------|:------------|:--------------------|:-----------------------------|
|[機密情報の種類](sensitive-information-type-entity-definitions.md)| キーワード、信頼度、近接度を含む確証的な証拠と共に、組み込みまたはカスタム正規表現または関数を使用して、機密データを特定します。| [組み込みの機密情報の種類をカスタマイズする](customize-a-built-in-sensitive-information-type.md)|
|[トレーニング可能な分類です (プレビュー)](classifier-getting-started-with.md)| 組み込み分類者のいずれかを使用するか、独自のコンテンツを使用して分類用にデータを分類します。 | [トレーニング可能な分類を作成する (プレビュー)](classifier-creating-a-trainable-classifier.md) |
|[データ分類](data-classification-overview.md) | 機密ラベル、保持ラベル、または組織で機密情報の種類として分類されているアイテムと、ユーザーが実行するアクションを識別します。  | [コンテンツ エクスプローラーの使用を開始する](data-classification-content-explorer.md)<br /><br /> [アクティビティ エクスプローラーの使用を開始する](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>データを保護する

暗号化、アクセス制限、視覚的なマーリングなど、柔軟な保護操作を適用するには、次の機能を使います。

|機能|どのような問題が解決しますか。|概要|
|:------|:------------|---------------------|:----------------------------|
|[機密ラベル](sensitivity-labels.md)| 組織の内外を移動する場合に、データのラベルを付けして保護するアプリ、サービス、デバイス全体の単一のソリューション <br /><br />シナリオ例: [Power BI で機密ラベルを適用および表示し、エクスポート時にデータを保護する](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|[ 機密ラベルの使用を開始する](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Windows コンピューターでは、ファイル エクスプローラーや PowerShell からすべてのファイル タイプのラベル付けや保護を含む追加の機能の機密ラベルを拡張します。<br /><br /> その他の機能の例: [Azure Information Protection 統合ラベル付けクライアント用のカスタム構成](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 統合ラベル付けクライアント管理者ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[二重キー暗号化](double-key-encryption.md)| どのような状況でも、保護されたコンテンツの暗号化を解除したり、地域的な境界内に暗号化キーを保持する必要がある規制要件に限ってもかもしれません | [二重キーの暗号化の展開](double-key-encryption.md#deploy-double-key-encryption)|
|[Office 365 Message Encryption](ome.md) (OME)| すべてのデバイスの任意のユーザーに送信される電子メール メッセージと添付ドキュメントを暗号化します。したがって、承認された受信者のみがメール付きの情報を読むことができます。  <br /><br />例: [Advanced Message Encryption によって暗号化された電子メールを取り消す](revoke-ome-encrypted-mail.md) | [Office 365 Message Encryption の使用を開始する](set-up-new-message-encryption-capabilities.md)|
|[カスタマー キーによるサービスの暗号化](customer-key-overview.md) | 権限のないシステムや担当者によるデータ表示からデータを表示しないようにし、Microsoft のデータ センターで BitLocker ディスクの暗号化を補足する | [Office 365 のカスタマー キーを設定する](customer-key-set-up.md)|
|[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|ユーザーがドキュメントをチェックアウトするときに、指定したポリシーに従ってそのファイルが許可されているユーザーのみが表示および使用できるように、ダウンロードしたファイルが保護されるかどうかを保護します。 | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Rights Management コネクタ](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Exchange または SharePoint Server を使用する既存のオンプレミス展開、または Windows Server とファイル分類インフラストラクチャ (FCI) を実行するファイル サーバーの保護のみ | [RMS コネクタを展開する手順](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection の統合ラベル付けスキャナー](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| オンプレミスのデータ ストアに格納されている機密情報を検出、ラベル、および保護する | [Azure Information Protection 統合ラベル付けスキャナーの構成とインストール](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| クラウド内のデータ ストアに格納されている機密情報を検出、ラベル、保護する | [クラウドに保存されている規制対象および機密データを検出、分類、ラベル付け、保護する](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft 情報保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|サード パーティ製のアプリおよびサービスに機密ラベルを拡張する。  <br /><br /> シナリオ例: [機密ラベルを設定および取得する (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Microsoft Information Protection (MIP) SDK のセットアップと構成](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>データの損失を防止する

機密情報の不用意な共有を防止するために、次の機能を使用します。


|機能|どのような問題が解決しますか。|概要|
|:------|:------------|:---------------------|:-----------------------------|
|[データ損失防止](data-loss-prevention-policies.md) (DLP)| 機密性の高いアイテムの意図しない共有を防止できます。 <br /><br />シナリオ例: [Microsoft Teams のチャットおよびチャネル メッセージでの機密情報の保護](dlp-microsoft-teams.md) | [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)|
|[エンドポイントのデータ損失防止 (プレビュー)](endpoint-dlp-learn-about.md)| DLP 機能を Windows 10 コンピューターで使用および共有されているアイテムに拡張します。 | [エンドポイント データ損失防止(プレビュー) を開始する](endpoint-dlp-getting-started.md)|
