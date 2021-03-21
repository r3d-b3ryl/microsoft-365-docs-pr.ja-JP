---
title: Microsoft 365 Defender で自動調査と対応機能を構成する
description: Microsoft 365 Defender で自己修復を使用して自動調査と応答を構成する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.date: 02/08/2021
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 05170c212e5e35d328e50dc0ee48d5f37e72869e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928666"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Microsoft 365 Defender で自動調査と対応機能を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender[](mtp-autoir.md)には、セキュリティ運用チームの時間と労力を節約できる強力な自動調査と対応機能が含まれています。 自己 [修復機能を使用](mtp-autoir.md#how-automated-investigation-and-self-healing-works)すると、これらの機能は、セキュリティ アナリストが脅威の調査と対応に必要な手順を模倣し、より速く、拡張する能力が高くなります。 この記事では、Microsoft 365 Defender で自動調査と対応を構成する方法について説明します。

自動調査および応答機能を構成するには、次の手順を実行します。

1. [前提条件を確認します](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [デバイス グループのオートメーション レベルを確認または変更します](#review-or-change-the-automation-level-for-device-groups)。
3. [365 でセキュリティ](#review-your-security-and-alert-policies-in-office-365)ポリシーとアラート ポリシー Officeします。
4. [Microsoft 365 Defender がオンになっていることを確認します](#make-sure-microsoft-365-defender-is-turned-on)。

次に、すべてのセットアップが終わると、アクション センターでアクションを表示 [および管理します](mtp-autoir-actions.md)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender での自動調査と対応の前提条件

|要件 |詳細 |
|:----|:----|
|サブスクリプションの要件 |これらのサブスクリプションの 1 つ。 <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Microsoft 365 E5 セキュリティ<br/>- Microsoft 365 A5 セキュリティ<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<p> [「Microsoft 365 Defender のライセンス要件」を参照してください](./prerequisites.md#licensing-requirements)。|
|ネットワーク要件 |- [Id の Microsoft Defender が有効](/azure-advanced-threat-protection/what-is-atp)<br/>- [構成済みの Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)<br/>- [Id 統合用 Microsoft Defender](/cloud-app-security/mdi-integration) |
|Windows コンピューターの要件 |- Windows 10、バージョン 1709 以降がインストール済み (「[Windows 10 リリース情報](/windows/release-information/)」を参照してください) <br/>- 次の脅威保護サービスが構成されています。<br/>- [エンドポイント用 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)<br/>- [Microsoft Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|電子メール コンテンツと電子メール ファイルOffice保護 |[Microsoft Defender for Office 365 が構成](../office-365-security/office-365-atp.md#configure-atp-policies) されている |
|アクセス許可 | 自動調査と対応機能を構成するには、Azure Active Directory ( ) または Microsoft 365 管理センター ( ) でグローバル管理者またはセキュリティ管理者の役割が割り当てられている [https://portal.azure.com](https://portal.azure.com) 必要があります [https://admin.microsoft.com](https://admin.microsoft.com) 。<p>保留中のアクションの確認、承認、拒否など、自動調査および応答機能を操作するために必要なアクセス許可を取得するには、「アクション センター タスクに必要なアクセス許可」 [を参照](mtp-action-center.md#required-permissions-for-action-center-tasks)してください。 |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>デバイス グループのオートメーション レベルを確認または変更する

自動調査を実行するかどうか、および修復アクションが自動的に実行されるのか、デバイスの承認時にのみ実行されるのかは、組織のデバイス グループ ポリシーなど、特定の設定によって異なります。 デバイス グループ ポリシーのオートメーション レベル セットを確認します。

1. Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。
2. [設定のアクセス **許可**  >  **] [デバイス**  >  **グループ] に移動します**。
3. デバイス グループ ポリシーを確認します。 特に、[修復レベル] **列を参照** してください。 完全 - 脅威 **を自動的に修復するを使用することをお勧めします**。  必要なオートメーションのレベルを取得するには、デバイス グループを作成または編集する必要がある場合があります。 このタスクのヘルプを表示するには、次の記事を参照してください。
   - [脅威の修復方法](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [デバイス グループの作成と管理](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>365 でセキュリティポリシーとアラート ポリシー Officeする

Microsoft は、特定のリスク [を特定するのに](../../compliance/alert-policies.md) 役立つ組み込みのアラート ポリシーを提供します。 これらのリスクには、Exchange 管理者のアクセス許可の悪用、マルウェアアクティビティ、外部および内部の潜在的な脅威、および情報ガバナンスのリスクが含まれます。 一部のアラートでは [、365 で自動調査とOffice発生する場合があります](../office-365-security/office-365-air.md)。 [365 の機能を使用Office Microsoft Defender が正](../office-365-security/office-365-atp.md)しく構成されていることを確認します。

特定のアラートとセキュリティ ポリシーによって自動調査がトリガーされる場合は、電子メールとコンテンツに対して修復アクションは自動的に実行されません。 代わりに、電子メールおよび電子メール コンテンツのすべての修復アクションは、アクション センターのセキュリティ運用チームによる承認を [待っています](mtp-action-center.md)。

365 Officeのセキュリティ設定は、電子メールとコンテンツの保護に役立ちます。 これらの設定を表示または変更するには、「脅威から保護する [」のガイダンスに従います](../office-365-security/protect-against-threats.md)。

1. Microsoft 365 セキュリティ センター ( ) で [https://security.microsoft.com](https://security.microsoft.com) 、[ポリシーの脅威の保護 **]**  >  **に移動します**。
2. 次のすべてのポリシーが構成されていることを確認します。 ヘルプと推奨事項を取得するには、「脅威から保護 [する」を参照してください](../office-365-security/protect-against-threats.md)。
   - [マルウェア対策 (Office 365)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [Defender for Office 365)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [安全な添付ファイル (Office 365)](../office-365-security/protect-against-threats.md#atp-safe-attachments-policies)
   - [セーフ リンク (Office 365)](../office-365-security/protect-against-threats.md#atp-safe-links-policies)
   - [スパム対策 (Office 365)](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. Microsoft [Defender for Office SharePoint、OneDrive、および Microsoft Teams の 365](../office-365-security/protect-against-threats.md#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) が有効になっていることを確認します。
4. メール保護 [のための 0 時間の自動削除が](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) 有効になってください。
5. (この手順は省略可能です)。Microsoft [365 コンプライアンス Office () の 365](../../compliance/alert-policies.md) アラート ポリシーを確認します [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 いくつかの既定のアラート ポリシーは、[脅威の管理] カテゴリに表示されます。 これらのアラートの中には、自動調査と応答をトリガーする場合があります。 詳細については、「既定のアラート [ポリシー」を参照してください](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Microsoft 365 Defender がオンになっていることを確認する

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Microsoft 365 セキュリティ センター ( ) に移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。
2. ナビゲーション ウィンドウで、**前の図** に示すように、インシデント、アクション センター、および **ハン** ティングを探します。
   - [インシデント] **、[****アクション** センター] 、および [ハンティング] が表示 **されている** 場合は、Microsoft 365 Defender がオンです。 デバイス グループのオートメーション [レベルを確認または変更する](#review-or-change-the-automation-level-for-device-groups) 手順 (この記事)を参照してください。
   - インシデント、アクション *センター* 、**または** ハンティングが表示されない場合は、Microsoft 365 Defender が有効ではない可能性があります。 この場合は、[アクション センターに [アクセスする] に進みます](mtp-action-center.md)。
3. ナビゲーション ウィンドウで、[設定]  >  **[Microsoft 365 Defender] を選択します**。 Microsoft 365 Defender がオンになっていることを確認します。 

> [!TIP]
> サポートが必要な場合 「On [Microsoft 365 Defender を有効にする」を参照してください](./mtp-enable.md)。

## <a name="next-steps"></a>次の手順

- [Microsoft 365 Defender の修復アクション](mtp-remediation-actions.md)
- [アクション センターにアクセスする](mtp-action-center.md)