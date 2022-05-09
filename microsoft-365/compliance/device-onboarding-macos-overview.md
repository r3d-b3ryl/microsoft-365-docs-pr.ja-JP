---
title: Microsoft 365 への macOS デバイスのオンボードに関する概要
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: macOS デバイスをコンプライアンス ソリューションにオンボードする方法について説明します
ms.openlocfilehash: 09a35e47a237639a722047b11c24f9b2d09cf51d
ms.sourcegitcommit: 5b321693214e3859f5af8f1774d2a5ff685ab3b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65014982"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview"></a>Microsoft 365 への macOS デバイスのオンボードに関する概要

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

MacOS デバイスは、Intuneまたは JAMF Proを使用して Microsoft Purview ソリューションにオンボードできます。 オンボード手順は、使用している管理ソリューションによって異なります。 macOS デバイスが既に Microsoft Defender for Endpoint (MDE) にオンボードされている場合は、手順が少なくなります。 適切な手順へのリンクについては、「 [次の手順](#next-steps) 」を参照してください。

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)

## <a name="before-you-begin"></a>開始する前に

macOS デバイス (Catalina 10.15 以降) で Endpoint DLP を使用する前に、次の記事を理解しておく必要があります。

- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)

DLP にまったく精通していない場合は、次の記事についても理解しておく必要があります。

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止 (DLP) の計画](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [データ損失防止ポリシー リファレンス](dlp-policy-reference.md#data-loss-prevention-policy-reference)

Insider Risk に慣れていない場合は、次の記事をよく理解しておく必要があります。

 - [インサイダー リスク管理](insider-risk-management.md)
 - [インサイダー リスク管理のための計画](insider-risk-management-plan.md#plan-for-insider-risk-management)

macOS デバイスは、Intuneまたは JAMF Proを使用して既に管理されている必要があります。
 
- Intuneにオンボードするには、「[展開ガイド: Microsoft Intuneで macOS デバイスを管理](/mem/intune/fundamentals/deployment-guide-platform-macos)する」と「[Intune ポータル サイトで Mac を登録する」を参照してください](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp)。 
- JAMF Proにオンボードするには、[JAMF Pro管理者ガイド](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)と [JAMF Pro Mac 用インストールと構成ガイド](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)を参照してください。
<!--- Install the v95+ Edge browser on your macOS devices--> 

### <a name="supported-browsers"></a>サポートされるブラウザー

エンドポイント DLP では、macOS Catalina 10.15 以降で次のブラウザーがサポートされます。

- Microsoft Edge (最新バージョン)
- Safari (最新バージョン、macOS のみ)
- Chrome (最新バージョン)
- Firefox (最新バージョン)

## <a name="licensing-guidance"></a>ライセンスに関するガイダンス

[情報保護のライセンスガイダンスMicrosoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)参照してください。

## <a name="activities-that-can-be-restricted-on-macos"></a>macOS で制限できるアクティビティ 

macOS デバイスが Microsoft Purview ソリューションにオンボードされたら、データ損失防止 (DLP) ポリシーを使用してこれらのアクションを監視および制限できます。

**USB リムーバブル メディアにコピーする** - 強制されると、このアクションは、エンドポイント デバイスから USB リムーバブル メディアへの保護されたファイルのコピーまたは移動をブロック、警告、監査します。 

**ネットワーク共有にコピーする** - このアクションは、エンドポイント デバイスから任意のネットワーク共有への保護されたファイルのコピーまたは移動をブロック、警告、または監査します。 

**印刷** – 強制されると、保護されたファイルがエンドポイント デバイスから印刷されたときに、このアクションがブロック、警告、または監査されます。 

**クリップボードにコピーする** - このアクションが適用されると、エンドポイント デバイス上のクリップボードにコピーされる保護されたファイル内のデータをブロック、警告、監査します。 

**クラウドにアップロード** – このアクションは、グローバル設定の許可または未承認のドメインの一覧に基づいて、保護されたファイルをクラウド サービスにアップロードできないようにしたり、許可したりしたときにブロック、警告、監査を行います。 このアクションが警告またはブロックに設定されている場合、他のブラウザー ([グローバル設定] の下の未承認のブラウザーの一覧で定義されている) は、ファイルへのアクセスをブロックされます。 

**未承認のアプリからアクセスされます** 。このアクションを適用すると、(グローバル設定で定義されている) 未承認のアプリの一覧にあるアプリケーションがエンドポイント デバイス上の保護されたファイルにアクセスできなくなります。 サンプル シナリオ 

## <a name="onboarding-devices-into-device-management"></a>デバイス管理へのデバイスのオンボーディング

デバイス上の機密アイテムを監視および保護する前に、デバイスの監視を有効にし、エンドポイントをオンボードしなければなりません。 これらのアクションはどちらも Microsoft Purview コンプライアンスポータルで行われます。

まだオンボーディングされていないデバイスをオンボーディングする場合は、適切なスクリプトをダウンロードして、それらのデバイスに導入します。 <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com)**設定ページを** 開き、[**デバイス監視を有効にする]** を選択します。

   > [!NOTE]
   > 通常、デバイスのオンボーディングが有効になるまで約60秒かかりますが、Microsoft サポートに連絡するまでに最大 30 分かかります。

2. コンプライアンス センターの設定ページを開き、[ **macOS デバイス監視を有効にする]** を選択します。

## <a name="next-steps"></a>次の手順

DLP センサー テレメトリを受信し、データ損失防止ポリシーを適用するには、デバイスを Microsoft Purview ソリューションにオンボードする必要があります。 

トピック | 説明
:---|:---
|[Intune を使用した Microsoft Purview ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-intune.md)|Intune を通じて管理される macOS デバイスの場合
|[Microsoft Defender for Endpoint のお客様向け Intune を使用したコンプライアンス ソリューションへの macOS デバイスのオンボードとオフボード](device-onboarding-offboarding-macos-intune-mde.md) |Intune を通じて管理され、Microsoft Defender for Endpoint (MDE) が展開されている macOS デバイスの場合
|[JAMF Proを使用して macOS デバイスを Microsoft Purview ソリューションにオンボードおよびオフボードする](device-onboarding-offboarding-macos-jamfpro.md) | JAMF Pro を通じて管理される macOS デバイスの場合
|[Microsoft Defender for Endpoint顧客向けの JAMF Proを使用して、macOS デバイスをコンプライアンス ソリューションにオンボードおよびオフボードする](device-onboarding-offboarding-macos-jamfpro-mde.md)|JAMF Pro を通じて管理され、Microsoft Defender for Endpoint (MDE) が展開されている macOS デバイスの場合


## <a name="related-topics"></a>関連項目

- [エンドポイントのデータ損失防止の使用](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft アプリ全体の DLP ポリシーヒントのサポート マトリックス](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
