---
title: Microsoft 365 Defender で自動調査および応答機能を構成する
description: Microsoft 365 Defender で自動調査と応答を自動修復して構成する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 3c8477ce16249cb4d21c736da60d619774175041
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123609"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Microsoft 365 Defender で自動調査および応答機能を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender は、強力な自動化された [調査と応答機能](mtp-autoir.md) を備えており、セキュリティ運用チームの時間と労力を大幅に節約できます。 自己復旧の場合、これらの機能はセキュリティアナリストが脅威を調査して対応するための手順に似ています。これにより、より迅速に、拡張性を高めることができます。 この記事では、Microsoft 365 Defender で自動調査と応答を構成する方法について説明します。

自動調査および応答機能を構成するには、次の手順を実行します。

1. [前提条件を確認](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)します。
2. [デバイスグループの自動化レベルを確認または変更](#review-or-change-the-automation-level-for-device-groups)します。
3. [Office 365 でセキュリティと警告のポリシーを確認して](#review-your-security-and-alert-policies-in-office-365)ください。
4. [Microsoft 365 Defender が有効になっていることを確認して](#make-sure-microsoft-365-defender-is-turned-on)ください。

すべての設定が完了したら、 [アクションセンターで [保留中] および [完了](#review-pending-and-completed-actions-in-the-action-center)したアクション] を確認します。 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender での自動調査および応答の前提条件

|要件 |詳細 |
|--|--|
|サブスクリプションの要件 |いずれかのサブスクリプション: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 セキュリティ<br/>-Microsoft 365 A5 セキュリティ<br/>-Office 365 E5 プラス Enterprise Mobility + Security E5 + Windows E5<br/><br/>「 [Microsoft 365 Defender ライセンスの要件](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)」を参照してください。|
|ネットワーク要件 |- Id が有効な[Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)<br/>- [Microsoft Cloud アプリのセキュリティ](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) が構成されている<br/>- [Id の Microsoft Defender と統合された microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows コンピューターの要件 |-Windows 10、バージョン1709以降がインストールされている (「 [windows 10 リリース情報](https://docs.microsoft.com/windows/release-information/)」を参照) 次の脅威保護サービスが構成されている。<br/>- [エンドポイントの Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子メールコンテンツと Office ファイルの保護 |[Microsoft Defender For Office 365 の](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 構成 |
|アクセス許可 |-自動調査および応答機能を構成するには、Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) または Microsoft 365 管理センター () のいずれかで、グローバル管理者またはセキュリティ管理者の役割が割り当てられている必要があり [https://admin.microsoft.com](https://admin.microsoft.com) ます。<br/><br/>-保留中のアクションの確認、承認、拒否など、自動化された調査および応答機能を使用するために必要なアクセス許可を取得するには、「 [アクションセンタータスクに必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)」を参照してください。 |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>デバイスグループの自動化レベルを確認または変更する

自動調査が実行されるかどうか、および修復アクションが自動で行われるか、またはデバイスの承認時にのみ適用されるかは、組織のデバイスグループポリシーなどの特定の設定によって決まります。 デバイスグループポリシーに設定されている自動化レベルを確認します。

1. Microsoft Defender セキュリティセンター () に移動し、 [https://securitycenter.windows.com](https://securitycenter.windows.com) サインインします。

2. [**設定**]  >  **アクセス許可**  >  **デバイスグループ** に移動します。 

3. デバイスのグループポリシーを確認します。 特に、 **修復レベル** 列を参照してください。 **完全修復脅威を自動的に** 使用することをお勧めします。  必要なオートメーションのレベルを取得するには、デバイスグループを作成または編集する必要がある場合があります。 このタスクに関するヘルプを表示するには、次の記事を参照してください。

   - [脅威が改善されるしくみ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [デバイスグループを作成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Office 365 でセキュリティと警告のポリシーを確認する

Microsoft は、特定のリスクを特定するのに役立つ組み込みの [通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) を提供しています。 これらのリスクには、Exchange 管理者権限の悪用、マルウェア活動、外部および内部の脅威、および情報ガバナンスのリスクがあります。 一部 [の通知では、Office 365 で自動調査と応答](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)がトリガーされることがあります。 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)機能が正しく構成されていることを確認してください。

特定の警告およびセキュリティポリシーで自動調査を開始することはできますが、電子メールとコンテンツに対しては修復処理は自動的に行われません。 代わりに、電子メールと電子メールコンテンツのすべての修復アクションは、 [アクションセンター](mtp-action-center.md)のセキュリティ運用チームによる承認を受けます。

Office 365 のセキュリティ設定電子メールとコンテンツの保護に役立ちます。 これらの設定を表示または変更するには、「 [脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」のガイダンスに従ってください。

1. Microsoft 365 セキュリティセンター () で [https://security.microsoft.com/](https://security.microsoft.com/) 、[ポリシーの **Policies**  >  **脅威保護**] に移動します。

2. 次のすべてのポリシーが構成されていることを確認してください。 ヘルプと推奨事項を取得するには、「 [脅威からの保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)」を参照してください。

   - [マルウェア対策 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Office 365 の Defender でのフィッシング対策](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [安全な添付ファイル (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [安全なリンク (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [スパム対策 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. [Microsoft Defender For Office 365 For SharePoint、OneDrive、Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads)が有効になっていることを確認してください。

5. [電子メール保護のゼロ時間の自動削除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop)が有効になっていることを確認します。 

8. (オプション)Microsoft 365 コンプライアンスセンター () で [Office 365 通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) を確認 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) してください。 いくつかの既定の通知ポリシーが脅威管理カテゴリにあります。 これらのアラートの中には、自動化された調査と応答をトリガーするものがあります。 詳細については、「 [Default alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)」を参照してください。
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Microsoft 365 Defender が有効になっていることを確認する

1. Microsoft 365 セキュリティセンター () に移動し、 [https://security.microsoft.com](https://security.microsoft.com) サインインします。

2. ナビゲーションウィンドウで、次の図に示すように、 **インシデント**、 **アクションセンター** **、および検索を探し** ます。

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP オン":::

   - **インシデント**、**アクションセンター**、**探し** ているものが表示される場合は、Microsoft 365 Defender が有効になっています。 手順について [は、「デバイスグループの自動化レベルを確認または変更する](#review-or-change-the-automation-level-for-device-groups) (この記事)」を参照してください。

   - **インシデント**、**アクションセンター**、または **探し** ているものが表示さ *れ* ない場合は、Microsoft 365 Defender が有効になっていない可能性があります。 この場合は、次の手順に進みます (この記事の「[保留中および完了したアクションを確認](#review-pending-and-completed-actions-in-the-action-center)する」を参照してください)。

3. ナビゲーションウィンドウで、[**設定**] [  >  **Microsoft 365 Defender**] を選択します。 Microsoft 365 Defender が有効になっていることを確認します。 

   サポートが必要な場合 「 [Microsoft 365 Defender を有効にする」を](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)参照してください。

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>アクションセンターで保留中および完了したアクションを確認する

Microsoft 365 Defender で自動調査と応答を構成した後、次の手順はアクションセンター () に移動することです [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。 そこで、保留中のアクションを確認して承認し、自動的に実行された修復アクションを確認することができます。 

[アクションセンターに移動](mtp-action-center.md)します。
