---
title: Microsoft 365 Defender で自動調査と応答機能を構成する
description: Microsoft 365 Defenderで自動復旧を使用して自動調査と応答を構成する
search.appverid: MET150
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 51efeb57c6670f9c798fa254bb0a6242b30c5700
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64944373"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Microsoft 365 Defender で自動調査と応答機能を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defenderには、セキュリティ運用チームの時間と労力を大幅に節約できる強力な[自動調査と対応機能](m365d-autoir.md)が含まれています。 [セルフヒーリング](m365d-autoir.md#how-automated-investigation-and-self-healing-works)を使用すると、これらの機能は、セキュリティ アナリストが脅威を調査して対応するために実行する手順を模倣し、より高速で、より多くのスケーリング機能を備えています。

この記事では、次の手順で<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で自動調査と応答を構成する方法について説明します。

1. [前提条件を確認します](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [デバイス グループの自動化レベルを確認または変更します](#review-or-change-the-automation-level-for-device-groups)。
3. [Office 365でセキュリティ ポリシーとアラート ポリシーを確認します](#review-your-security-and-alert-policies-in-office-365)。
4. [Microsoft 365 Defenderがオンになっていることを確認します](#make-sure-microsoft-365-defender-is-turned-on)。

その後、すべての設定が完了したら、 [アクション センターで修復アクションを表示および管理](m365d-autoir-actions.md)できます。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defenderでの自動調査と対応の前提条件

<br>

****

|要件|詳細|
|---|---|
|サブスクリプションの要件|これらのサブスクリプションの 1 つ: <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E5 Security アドオンを使用したMicrosoft 365 E3</li><li>Microsoft 365 A5 セキュリティ アドオンを使用したMicrosoft 365 A3</li><li>Office 365 E5 プラス Enterprise Mobility + Security E5 + Windows E5</li></ul> <p> [Microsoft 365 Defenderライセンス要件に関するページを](./prerequisites.md#licensing-requirements)参照してください。|
|ネットワーク要件|<ul><li>[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)有効</li><li>[Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)構成済み</li><li>[Microsoft Defender for Identity統合](/cloud-app-security/mdi-integration)</li></ul>|
|Windowsデバイス要件|<ul><li>Windows 11</li><li>Windows 10、バージョン 1709 以降がインストールされている ([リリース情報Windows](/windows/release-information/)参照)</li><li>次の脅威保護サービスが構成されています。<ul><li>[Microsoft Defender for Endpoint](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|電子メール コンテンツとOffice ファイルの保護|[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies)構成済み|
|アクセス許可|自動調査と対応機能を構成するには、Azure Active Directory () またはMicrosoft 365 管理センター (<https://portal.azure.com><https://admin.microsoft.com>) にグローバル管理者またはセキュリティ管理者ロールが割り当てられている必要があります。 <p> 保留中のアクションの確認、承認、拒否などの自動調査機能と応答機能を操作するために必要なアクセス許可を取得するには、「 [アクション センター タスクに必要なアクセス許可](m365d-action-center.md#required-permissions-for-action-center-tasks)」を参照してください。|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>デバイス グループの自動化レベルを確認または変更する

自動調査が実行されるか、修復アクションが自動的に実行されるか、デバイスの承認時にのみ実行されるかは、組織のデバイス グループ ポリシーなどの特定の設定によって異なります。 デバイス グループ ポリシーの構成済みの自動化レベルを確認します。

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. **[アクセス許可****] の [設定** > **EndpointsDevice** >  **グループ**] に移動します。

3. デバイス グループ ポリシーを確認します。 特に、 **Automation レベル** の列を確認します。 **脅威を自動的に修復するには、完全な修復** を使用することをお勧めします。  必要な自動化レベルを得るために、デバイス グループを作成または編集することが必要な場合があります。 このタスクのヘルプを表示するには、次の記事を参照してください。
   - [脅威の修復方法](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [デバイス グループの作成と管理](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Office 365でセキュリティ ポリシーとアラート ポリシーを確認する

Microsoft には、特定のリスクを特定するのに役立つ組み込みの [アラート ポリシー](../../compliance/alert-policies.md) が用意されています。 これらのリスクには、Exchange管理者のアクセス許可の悪用、マルウェア アクティビティ、潜在的な外部および内部の脅威、および情報ガバナンス のリスクが含まれます。 一部のアラートでは、[Office 365で自動調査と応答を](../office-365-security/office-365-air.md)トリガーできます。 [Defender for Office 365](../office-365-security/defender-for-office-365.md)機能が正しく構成されていることを確認します。

特定のアラートとセキュリティ ポリシーは自動調査をトリガーできますが、 *電子メールとコンテンツに対して自動的に修復アクションは実行されません*。 代わりに、電子メールおよび電子メール コンテンツに対するすべての修復アクションが [、アクション センター](m365d-action-center.md)のセキュリティ運用チームによる承認を待ちます。

Office 365のセキュリティ設定は、電子メールとコンテンツの保護に役立ちます。 これらの設定を表示または変更するには、「 [脅威から保護する](../office-365-security/protect-against-threats.md)」のガイダンスに従います。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、[**ポリシー] & [ルール** \> **の脅威] ポリシー** に移動します。

2. 次のすべてのポリシーが構成されていることを確認します。 ヘルプと推奨事項については、「 [脅威から保護する](/microsoft-365/security/office-365-security/protect-against-threats)」を参照してください。
   - [マルウェア対策](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [フィッシング詐欺対策](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [添付ファイル保護](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [リンク保護](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [スパム対策](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. [SharePoint、OneDrive、Microsoft Teamsの添付ファイルのセーフ](../office-365-security/mdo-for-spo-odb-and-teams.md)がオンになっていることを確認します。

4. [Exchange Onlineのゼロ時間自動消去 (ZAP)](../office-365-security/zero-hour-auto-purge.md) が有効になっていることを確認します。

5. (この手順は省略可能です)。Microsoft Purview コンプライアンス ポータル ()[https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) で[Office 365アラート ポリシー](../../compliance/alert-policies.md)を確認します。 脅威管理カテゴリには、いくつかの既定のアラート ポリシーがあります。 これらのアラートの一部は、自動調査と応答をトリガーする可能性があります。 詳細については、「 [既定のアラート ポリシー](../../compliance/alert-policies.md#default-alert-policies)」を参照してください。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Microsoft 365 Defenderがオンになっていることを確認する

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="Microsoft 365 Defenderがオンになっている場合、Microsoft 365 Defender ポータルの左側のナビゲーション ウィンドウ" lightbox="../../media/mtp-enable/mtp-on.png":::

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>にサインインする

2. ナビゲーション ウィンドウで、前の図に示すように、 **インシデント &アラート**、 **ハンティング**、 **アクション センター** を探します。
   - **インシデント&アラート**、**ハンティング**、**アクション センター** が表示された場合は、Microsoft 365 Defenderがオンになります。 この記事の「 [デバイス グループの自動化レベルを確認または変更する](#review-or-change-the-automation-level-for-device-groups) 」セクションを参照してください。
   - **インシデント**、**アクション センター**、または **ハンティング** が表示 *されない* 場合は、Microsoft 365 Defenderがオンになっていない可能性があります。 この場合は、 [アクション センターにアクセスします](m365d-action-center.md)。

> [!TIP]
> お困りの際は、 [「Microsoft 365 Defenderを有効にする」](m365d-enable.md)を参照してください。

## <a name="next-steps"></a>次の手順

- [Microsoft 365 Defenderの修復アクション](m365d-remediation-actions.md)
- [アクション センターにアクセスする](m365d-action-center.md)
