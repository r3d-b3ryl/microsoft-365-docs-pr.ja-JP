---
title: Microsoft 365 Defender で自動調査と応答機能を構成する
description: 自動調査と応答を構成するには、自動修復機能をMicrosoft 365 Defender
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 3a2a06b48da1f83e82fd9f1a1293e9484517bd0e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162376"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Microsoft 365 Defender で自動調査と応答機能を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defenderには、セキュリティ[運用](m365d-autoir.md)チームの時間と労力を節約できる強力な自動調査と対応機能が含まれています。 自己 [修復機能を使用](m365d-autoir.md#how-automated-investigation-and-self-healing-works)すると、これらの機能は、セキュリティ アナリストが脅威の調査と対応に必要な手順を模倣し、より速く、拡張する能力が高くなります。

この記事では、次の手順に従って、自動調査と応答を構成する方法Microsoft 365 Defender説明します。

1. [前提条件を確認します](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。
2. [デバイス グループのオートメーション レベルを確認または変更します](#review-or-change-the-automation-level-for-device-groups)。
3. [[セキュリティとアラート ポリシー] を [Office 365] で確認します](#review-your-security-and-alert-policies-in-office-365)。
4. [この設定Microsoft 365 Defenderオンになっていることを確認します](#make-sure-microsoft-365-defender-is-turned-on)。

その後、すべてのセットアップが終わると、アクション [センターで修復アクションを表示および管理できます](m365d-autoir-actions.md)。

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>データの自動調査と対応の前提条件Microsoft 365 Defender

<br>

****

|要件|詳細|
|---|---|
|サブスクリプションの要件|これらのサブスクリプションの 1 つ。 <ul><li>Microsoft 365 E5</li><li>Microsoft 365 A5</li><li>Microsoft 365 E3アドオンMicrosoft 365 E5 Securityを使用する</li><li>Microsoft 365 A3セキュリティ Microsoft 365 A5を使用する</li><li>Office 365 E5 E5 プラス Enterprise Mobility + Security E5 Windows E5</li></ul> <p> 「[ライセンスMicrosoft 365 Defender」を参照してください](./prerequisites.md#licensing-requirements)。|
|ネットワーク要件|<ul><li>[Id の Microsoft Defender が有効](/azure-advanced-threat-protection/what-is-atp)</li><li>[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)構成済み</li><li>[Id 統合用 Microsoft Defender](/cloud-app-security/mdi-integration)</li></ul>|
|Windowsの要件|<ul><li>Windows 11</li><li>Windows 10バージョン 1709 以降がインストールされている (リリース[情報Windows参照)](/windows/release-information/)</li><li>構成されている脅威保護サービスは次のとおりです。<ul><li>[Microsoft Defender for Endpoint](../defender-endpoint/configure-endpoints.md)</li><li>[Microsoft Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)</li></ul></li></ul>|
|電子メール コンテンツと電子メール ファイルOffice保護|[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies)構成済み|
|アクセス許可|自動調査および応答機能を構成するには、グローバル管理者またはセキュリティ管理者の役割が Azure Active Directory ( ) または Microsoft 365 管理センター ( ) のどちらかに割 <https://portal.azure.com> り当てられている必要があります <https://admin.microsoft.com> 。 <p> 保留中のアクションの確認、承認、拒否など、自動調査および応答機能を操作するために必要なアクセス許可を取得するには、「アクション センター タスクに必要なアクセス許可」 [を参照](m365d-action-center.md#required-permissions-for-action-center-tasks)してください。|
|

## <a name="review-or-change-the-automation-level-for-device-groups"></a>デバイス グループのオートメーション レベルを確認または変更する

自動調査を実行するかどうか、および修復アクションが自動的に実行されるのか、デバイスの承認時にのみ実行されるのかは、組織のデバイス グループ ポリシーなど、特定の設定によって異なります。 デバイス グループ ポリシーの構成済みのオートメーション レベルを確認します。

1. [パスワード] ( ) にMicrosoft Defender セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。

2. [アクセス許可  >  **設定] デバイス グループ**  >  **に移動します**。

3. デバイス グループ ポリシーを確認します。 特に、[修復レベル] **列を参照** してください。 完全 - 脅威 **を自動的に修復するを使用することをお勧めします**。  必要なオートメーションのレベルを取得するには、デバイス グループを作成または編集する必要がある場合があります。 このタスクのヘルプを表示するには、次の記事を参照してください。
   - [脅威の修復方法](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [デバイス グループの作成と管理](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>セキュリティ ポリシーとアラート ポリシーを確認Office 365

Microsoft は、特定のリスク [を特定するのに](../../compliance/alert-policies.md) 役立つ組み込みのアラート ポリシーを提供します。 これらのリスクには、Exchangeアクセス許可の悪用、マルウェアアクティビティ、外部および内部の潜在的な脅威、および情報ガバナンスのリスクが含まれます。 一部のアラートは、[自動調査と](../office-365-security/office-365-air.md)応答をトリガー Office 365。 すべての機能の[Defender がOffice 365](../office-365-security/defender-for-office-365.md)構成されていることを確認します。

特定のアラートとセキュリティ ポリシーによって自動調査がトリガーされる場合は、電子メールとコンテンツに対して修復アクション *は自動的に実行されません*。 代わりに、電子メールおよび電子メール コンテンツのすべての修復アクションは、アクション センターのセキュリティ運用チームによる承認を [待っています](m365d-action-center.md)。

メールとコンテンツOffice 365保護するために役立つセキュリティ設定。 これらの設定を表示または変更するには、「脅威から保護する [」のガイダンスに従います](../office-365-security/protect-against-threats.md)。

1. [ポータル] Microsoft 365 Defenderで、[ポリシー <https://security.microsoft.com> とルール **の脅威&に** \> **移動します**。

2. 次のすべてのポリシーが構成されていることを確認します。 ヘルプと推奨事項を取得するには、「脅威から保護 [する」を参照してください](/microsoft-365/security/office-365-security/protect-against-threats)。
   - [マルウェア対策](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection-in-eop)
   - [フィッシング対策](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
   - [添付ファイル保護](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [リンク保護](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [スパム対策](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection-in-eop)

3. [添付[セーフ] がSharePoint、OneDrive、Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md)になっていることを確認します。

4. ゼロ時間[自動削除 (ZAP) が有効Exchange Online](../office-365-security/zero-hour-auto-purge.md)確認します。

5. (この手順は省略可能です)。[警告[Office 365ポリシー]](../../compliance/alert-policies.md) () で確認Microsoft 365 コンプライアンス センターします [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 。 いくつかの既定のアラート ポリシーは、[脅威の管理] カテゴリに表示されます。 これらのアラートの中には、自動調査と応答をトリガーする場合があります。 詳細については、「既定のアラート [ポリシー」を参照してください](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>有効になっているMicrosoft 365 Defender確認する

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on。":::

1. ポータル () にサインインMicrosoft 365 Defenderします [https://security.microsoft.com](https://security.microsoft.com) 。

2. ナビゲーション ウィンドウで、前の図に示 **&、** アラート、ハンティング、およびアクション センターの [インシデント] を探します。
   - [インシデントと **警告] 、&、****および** アクション センターが表示される場合は、Microsoft 365 Defenderがオンです。 この記事 [の「デバイス グループのオートメーション レベルを確認または変更する](#review-or-change-the-automation-level-for-device-groups) 」セクションを参照してください。
   - [インシデント]  **、[アクション** センター] 、または **[ハン** ティング] が表示されない場合はMicrosoft 365 Defenderが有効にされていない可能性があります。  この場合は、 [アクション センターにアクセスします](m365d-action-center.md)。

3. ナビゲーション ウィンドウで、[次の操作]**を**  >  **設定Microsoft 365 Defender。** 有効になっているMicrosoft 365 Defender確認します。

> [!TIP]
> お困りの際は、 「[電源を入Microsoft 365 Defender」 を参照してください](m365d-enable.md)。

## <a name="next-steps"></a>次の手順

- [[修復アクション] Microsoft 365 Defender](m365d-remediation-actions.md)
- [アクション センターにアクセスする](m365d-action-center.md)
