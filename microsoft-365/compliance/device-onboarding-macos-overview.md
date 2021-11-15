---
title: Microsoft 365 への macOS デバイスのオンボードに関する概要 (プレビュー)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: コンプライアンス ソリューションへの macOS デバイスのオンボーディングについて
ms.openlocfilehash: fbf29e0d66bf31d058cede69aba9fe0c7814a3a7
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963253"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>Microsoft 365 への macOS デバイスのオンボードに関する概要 (プレビュー)

MacOS デバイスは、Intune または JAMF Microsoft 365を使用して、コンプライアンス ソリューションにオンボードPro。 オンボーディング手順は、使用している管理ソリューションによって異なります。 macOS デバイスが Microsoft Defender for Endpoint (MDE) に既にオンボードされている場合は、手順が少なくなっています。 適切 [な手順への](#next-steps) リンクについては、「次の手順」を参照してください。

**適用対象:**

- [Microsoft 365 エンドポイントのデータ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>はじめに

macOS デバイス (Catalina 10.15 以降) での Endpoint DLP の使用を開始する前に、次の記事を理解する必要があります。

- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

DLP に精通していない場合は、次の記事も理解する必要があります。

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止 (DLP) の計画](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [データ損失防止ポリシーリファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference)

Insider Risk に精通していない場合は、次の記事について理解する必要があります。

 - [インサイダー リスク管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
 - [インサイダー リスク管理のための計画](insider-risk-management-plan.md#plan-for-insider-risk-management)

macOS デバイスは、Intune または JAMF を使用して既に管理されている必要Pro。
 
- Intune にオンボードするには、「Deployment [guide: Manage macOS](/mem/intune/fundamentals/deployment-guide-platform-macos) devices in Microsoft Intune」および「Mac をデバイスに登録する」[をIntune ポータル サイト。](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- JAMF ProにPro [JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) Proインストールおよび構成ガイド」[を参照してください。](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- macOS デバイスに v95+ Edge ブラウザーをインストールする 

## <a name="licensing-guidance"></a>ライセンスガイダンス

「情報保護[Microsoft 365ライセンス ガイダンス」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

## <a name="activities-that-can-be-restricted-on-macos"></a>macOS で制限できるアクティビティ 

macOS デバイスがコンプライアンス ソリューションにオンボードMicrosoft 365、データ損失防止 (DLP) ポリシーを使用してこれらのアクションを監視および制限できます。

**USB リムーバブル メディアへの** コピー – 適用された場合、このアクションは、保護されたファイルをエンドポイント デバイスから USB リムーバブル メディアへのコピーまたは移動をブロック、警告、または監査します。 

**ネットワーク共有へのコピー** – 適用される場合、このアクションは、保護されたファイルのエンドポイント デバイスからネットワーク共有へのコピーまたは移動をブロック、警告、または監査します。 

**Print** – 強制された場合、保護されたファイルがエンドポイント デバイスから印刷される場合、このアクションはブロック、警告、または監査を行います。 

**クリップボードにコピー** する – 適用された場合、エンドポイント デバイス上のクリップボードにコピーされる保護されたファイル内のデータをブロック、警告、または監査します。 

**アップロード**– このアクションは、保護されたファイルがグローバル設定の許可/許可されていないドメイン リストに基づいてクラウド サービスへのアップロードを禁止または許可されている場合にブロック、警告、または監査を行います。 このアクションを警告またはブロックに設定すると、他のブラウザー ([グローバル設定] の [許可されていないブラウザー] リストで定義) がファイルへのアクセスをブロックされます。 

**許可されていないアプリ** からアクセスします。このアクションを適用すると、許可されていないアプリの一覧 (グローバル設定で定義されている) にあるアプリケーションがエンドポイント デバイス上の保護されたファイルにアクセスできません。 サンプル シナリオ 

## <a name="onboarding-devices-into-device-management"></a>デバイス管理へのデバイスのオンボーディング

デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。 これらのアクションはどちらも Microsoft 365 コンプライアンスポータルで行われます。

まだオンボーディングされていないデバイスをオンボーディングする場合は、適切なスクリプトをダウンロードして、それらのデバイスに導入します。 <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. [Microsoft コンプライアンス [センター] ページを開](https://compliance.microsoft.com)**設定[** デバイスの監視を **有効にする] を選択します**。

   > [!NOTE]
   > 通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。

2. コンプライアンスセンターの設定ページを開き、[**オンボードデバイス**]を選択します。

   > [!div class="mx-imgBorder"]
   > ![デバイス管理を有効にする。](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

## <a name="next-steps"></a>次の手順

DLP センサーの利用統計情報をMicrosoft 365データ損失防止ポリシーを適用するには、コンプライアンス ソリューションにデバイスをオンボーディングする必要があります。 

トピック | 説明
:---|:---
|[Intune を使用した Microsoft 365 コンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)|Intune を通じて管理される macOS デバイスの場合
|[Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview) |Intune を通じて管理され、Microsoft Defender for Endpoint (MDE) が展開されている macOS デバイスの場合
|[JAMF Pro を使用した Microsoft 365 コンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview) | JAMF Pro を通じて管理される macOS デバイスの場合
|[Microsoft Defender for Endpoint のお客様向け JAMF Pro を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード (プレビュー)](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)|JAMF Pro を通じて管理され、Microsoft Defender for Endpoint (MDE) が展開されている macOS デバイスの場合


## <a name="related-topics"></a>関連トピック

- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft アプリ全体の DLP ポリシー ヒントのサポート マトリックス](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
