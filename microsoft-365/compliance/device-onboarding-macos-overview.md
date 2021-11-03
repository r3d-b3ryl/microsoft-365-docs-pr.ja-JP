---
title: macOS デバイスをオンボードMicrosoft 365概要 (プレビュー)
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
ms.openlocfilehash: b9e04b95a0daa123a7e5a8c7863d6477ab2ccf15
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661910"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>macOS デバイスをオンボードMicrosoft 365概要 (プレビュー)

MacOS デバイスは、Intune または JAMF Microsoft 365を使用して、コンプライアンス ソリューションにオンボードPro。 オンボーディング手順は、使用している管理ソリューションによって異なります。 macOS デバイスが Microsoft Defender for Endpoint (MDE) に既にオンボードされている場合は、手順が少なくなっています。 適切 [な手順への](#next-steps) リンクについては、「次の手順」を参照してください。

## <a name="get-registered"></a>登録を取得する

この機能にアクセスするには、テナントを Microsoft に登録する必要があります。 macOS[のサポートに登録Microsoft 365を参照してください](https://aka.ms/Ignite2021DLP)。

**適用対象:**

- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- [インサイダー リスクの管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
<!--- [Insider risk management](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)-->

## <a name="before-you-begin"></a>はじめに

macOS デバイス (Catalina 10.15 以降) での Endpoint DLP の使用を開始する前に、次の記事を理解する必要があります。

- [Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [エンドポイント データ損失防止の使用を開始する](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

DLP に精通していない場合は、次の記事も理解する必要があります。

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止 (DLP) の計画](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [データ損失防止ポリシーリファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference)

macOS デバイスは、Intune または JAMF を使用して既に管理されている必要Pro。
 
- Intune にオンボードするには、「Deployment [guide: Manage macOS](/mem/intune/fundamentals/deployment-guide-platform-macos) devices in Microsoft Intune」および「Mac をデバイスに登録する」[をIntune ポータル サイト。](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- JAMF ProにPro [JAMF](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) Proインストールおよび構成ガイド」[を参照してください。](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- macOS デバイスに v95+ Edge ブラウザーをインストールする 

## <a name="licensing-guidance"></a>ライセンスガイダンス

「情報保護[Microsoft 365ライセンス ガイダンス」を参照してください。](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="activities-that-can-be-restricted-on-macos"></a>macOS で制限できるアクティビティ 

macOS デバイスがコンプライアンス ソリューションにオンボードMicrosoft 365、データ損失防止 (DLP) ポリシーを使用してこれらのアクションを監視および制限できます。

**USB リムーバブル メディアへの** コピー – 適用された場合、このアクションは、保護されたファイルをエンドポイント デバイスから USB リムーバブル メディアへのコピーまたは移動をブロック、警告、または監査します。 

**ネットワーク共有へのコピー** – 適用される場合、このアクションは、保護されたファイルのエンドポイント デバイスからネットワーク共有へのコピーまたは移動をブロック、警告、または監査します。 

**Print** – 強制された場合、保護されたファイルがエンドポイント デバイスから印刷される場合、このアクションはブロック、警告、または監査を行います。 

**クリップボードにコピー** する – 適用された場合、エンドポイント デバイス上のクリップボードにコピーされる保護されたファイル内のデータをブロック、警告、または監査します。 

**アップロード**– このアクションは、保護されたファイルがグローバル設定の許可/許可されていないドメイン リストに基づいてクラウド サービスへのアップロードを禁止または許可されている場合にブロック、警告、または監査を行います。 このアクションを警告またはブロックに設定すると、他のブラウザー ([グローバル設定] の [許可されていないブラウザー] リストで定義) がファイルへのアクセスをブロックされます。 

**許可されていないアプリ** からアクセスします。このアクションを適用すると、許可されていないアプリの一覧 (グローバル設定で定義されている) にあるアプリケーションがエンドポイント デバイス上の保護されたファイルにアクセスできません。 サンプル シナリオ 

## <a name="next-steps"></a>次の手順

DLP センサーの利用統計情報をMicrosoft 365データ損失防止ポリシーを適用するには、コンプライアンス ソリューションにデバイスをオンボーディングする必要があります。 

- Intune を介して管理される macOS デバイスについては、「オンボードおよびオフボードの macOS デバイスから Intune を使用したコンプライアンス Microsoft 365コンプライアンス ソリューションへのアクセス[(プレビュー)」を参照してください。](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)

- Intune を介して管理され、Microsoft Defender for Endpoint (MDE) が展開されている macOS デバイスについては、「Intune for Microsoft Defender for Endpoint カスタマー (プレビュー)を使用したコンプライアンス ソリューションへのオンボードおよびオフボード[macOS](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview)デバイス」を参照してください。

- JAMF Pro を介して管理される macOS デバイスについては、「JAMF Pro を使用した Microsoft 365 コンプライアンス ソリューションへのオンボードおよびオフボードの macOS デバイス[(プレビュー)」](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview)を参照してください。

- JAMF Pro を介して管理され、Microsoft Defender for Endpoint (MDE) が展開されている macOS デバイスについては、「Microsoft Defender for Endpoint のお客様向け[JAMF Pro](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)を使用したコンプライアンス ソリューションへのオンボードおよびオフボード macOS デバイス (プレビュー)」を参照してください。


## <a name="related-topics"></a>関連トピック

- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft アプリ全体の DLP ポリシー ヒントのサポート マトリックス](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
