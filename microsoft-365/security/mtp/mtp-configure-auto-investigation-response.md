---
title: Microsoft 365 Defender で自動調査および対応機能を構成する
description: Microsoft 365 Defender で自動修復による自動調査と対応を構成する
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
ms.openlocfilehash: 12f71011e28d5c8c8287146670282a86a77781ff
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682983"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Microsoft 365 Defender で自動調査および対応機能を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 365 Defender[](mtp-autoir.md)には、セキュリティ運用チームの時間と労力を節約できる強力な自動調査および対応機能が含まれています。 自己修復により、これらの機能は、セキュリティ アナリストが脅威を調査して対応するために実行する手順を模倣し、より速く、さらに拡張する機能を備えたものになります。 この記事では、Microsoft 365 Defender で自動調査と対応を構成する方法について説明します。

自動調査および対応機能を構成するには、次の手順を実行します。

1. [前提条件を確認します](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [デバイス グループのオートメーション レベルを確認または変更します](#review-or-change-the-automation-level-for-device-groups)。
3. [Office 365 でセキュリティ ポリシーとアラート ポリシーを確認します](#review-your-security-and-alert-policies-in-office-365)。
4. [Microsoft 365 Defender が有効になっていることを確認します](#make-sure-microsoft-365-defender-is-turned-on)。

その後、すべてのセットアップが完了したら、アクション センターで保留中のアクションと [完了したアクションを確認します](#review-pending-and-completed-actions-in-the-action-center)。 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender での自動調査と対応の前提条件

|要件 |詳細 |
|--|--|
|サブスクリプションの要件 |サブスクリプションの 1 つ: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5 セキュリティ<br/>- Microsoft 365 A5 セキュリティ<br/>- Office 365 E5+ Enterprise Mobility + Security E5 + Windows E5<br/><br/>[Microsoft 365 Defender のライセンス要件をご覧ください](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)。|
|ネットワーク要件 |- [Id に対する Microsoft Defender の](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 有効化<br/>- [Microsoft Cloud App Security の](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 構成<br/>- [Id 用 Microsoft Defender と統合された Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows コンピューターの要件 |- 次の脅威保護サービスが構成された Windows 10 バージョン 1709 以降がインストールされている [(Windows 10](https://docs.microsoft.com/windows/release-information/)のリリース情報を参照)<br/>- [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子メールコンテンツと電子メール ファイルOffice保護 |[Microsoft Defender for Office 365 の](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 構成 |
|アクセス許可 |- 自動調査および対応機能を構成するには、Azure Active Directory ( ) または Microsoft 365 管理センター ( ) で、グローバル管理者またはセキュリティ管理者の役割が割り当てられている必要 [https://portal.azure.com](https://portal.azure.com) があります [https://admin.microsoft.com](https://admin.microsoft.com) 。<br/><br/>- レビュー、承認、保留中のアクションの拒否など、自動調査および対応機能を操作するために必要なアクセス許可を取得するには、「アクション センターのタスクに必要なアクセス許可」を参照[してください。](mtp-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>デバイス グループの自動化レベルを確認または変更する

自動調査を実行するかどうか、および修復アクションが自動的に実行されるかどうか、またはデバイスの承認時にのみ実行されるかどうかは、組織のデバイス グループ ポリシーなどの特定の設定によって異なります。 デバイス グループ ポリシーのオートメーション レベル セットを確認します。

1. Microsoft Defender セキュリティ センター ( ) に移動し [https://securitycenter.windows.com](https://securitycenter.windows.com) 、サインインします。

2. [設定のアクセス **許可**  >  **] デバイス グループ**  >  **に移動します**。 

3. デバイス グループ ポリシーを確認します。 特に、修復レベルの **列を確認** します。 完全 - 脅威 **を自動的に修復するを使用することをお勧めします**。  必要なオートメーションのレベルを取得するには、デバイス グループを作成または編集する必要がある場合があります。 このタスクのヘルプを表示するには、次の記事を参照してください。

   - [脅威の修復方法](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [デバイス グループの作成と管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Office 365 でセキュリティ ポリシーとアラート ポリシーを確認する

Microsoft は、特定のリスク [の特定に](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 役立つ組み込みのアラート ポリシーを提供しています。 これらのリスクには、Exchange 管理者アクセス許可の不正使用、マルウェア アクティビティ、潜在的な外部および内部の脅威、情報ガバナンスのリスクが含まれます。 一部のアラートは [、365 年 1 月 365 日Office調査と対応をトリガーします](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。 Microsoft Defender for [Office 365 の機能が正しく](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 構成されていることを確認します。

特定のアラートとセキュリティ ポリシーによって自動調査がトリガーされる可能性はあるが、メールとコンテンツに対して修復アクションは自動的に実行されません。 代わりに、メールとメール コンテンツに対する修復アクションはすべて、アクション センターのセキュリティ運用チームによる承認を [待っています](mtp-action-center.md)。

Office 365 のセキュリティ設定は、電子メールとコンテンツの保護に役立ちます。 これらの設定を表示または変更するには、「脅威から保護する」の [ガイダンスに従います](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。

1. Microsoft 365 セキュリティ センター ( ) で [https://security.microsoft.com/](https://security.microsoft.com/) **、Policies** Threat Protection に  >  **移動します**。

2. 次のすべてのポリシーが構成されていることを確認します。 ヘルプと推奨事項については、「脅威から保護 [する」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。

   - [マルウェア対策 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Defender for Office 365) のフィッシング対策](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [安全な添付ファイル (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [安全なリンク (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [スパム対策 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Microsoft [Defender for Office 365 for SharePoint、OneDrive、Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) がオンになっていることを確認します。

5. メール保護 [の 0 時間自動消去が有効](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) な場合。 

8. (省略可能)。Microsoft [365 コンプライアンス Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) アラート ポリシーを確認します [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 脅威管理カテゴリには、いくつかの既定のアラート ポリシーがあります。 これらのアラートの一部は、自動調査と対応をトリガーできます。 詳細については、「既定のアラート [ポリシー」を参照してください](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)。
 
## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Microsoft 365 Defender が有効になっていることを確認する

1. Microsoft 365 セキュリティ センター ( ) に移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。

2. ナビゲーション ウィンドウで、次の図に示すように、インシデント、アクション センター、および **ハン** ティングを探します。

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

   - インシデント、**アクション センター**、**および** ハンティングが表示された場合は、Microsoft 365 Defender が有効です。 デバイス グループのオートメーション [レベルを確認または変更する手順](#review-or-change-the-automation-level-for-device-groups) については、この記事を参照してください。

   - インシデント、アクション *センター* 、**または** ハンティングが表示されない場合は、Microsoft 365 Defender が有効ではない可能性があります。 この場合は、次の手順に進みます (この記事では、保留中の[アクションと完了した](#review-pending-and-completed-actions-in-the-action-center)アクションを確認します)。

3. ナビゲーション ウィンドウで、[  >  **設定] Microsoft 365 Defender を選択します**。 Microsoft 365 Defender が有効になっていることを確認します。 

   サポートが必要な場合 [「Microsoft 365 Defender を有効にする」をご覧ください](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)。

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>アクション センターで保留中のアクションと完了したアクションを確認する

Microsoft 365 Defender で自動調査と対応を構成した後、次の手順はアクション センター () にアクセスします [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。 そこで、保留中のアクションを確認および承認し、自動的または手動で実行された修復アクションを確認できます。 

[アクション センターにアクセスします](mtp-action-center.md)。
