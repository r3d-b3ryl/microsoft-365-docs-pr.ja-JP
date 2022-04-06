---
title: Microsoft Defender での自動調査と対応が可能Office 365
keywords: AIR、autoIR、Microsoft Defender for Endpoint、自動化、調査、対応、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender の自動調査および応答機能を使用して、ユーザーにOffice 365。
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 70a5eba3eb78878cc1f15bdd711a3331e9af870a
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680888"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender の自動調査と応答 (AIR) Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](defender-for-office-365.md)には、セキュリティ運用チームの時間と労力を節約できる強力な自動調査と応答 (AIR) 機能が含まれています。 アラートがトリガーされると、セキュリティ運用チームがそれらのアラートを確認、優先順位付け、応答する必要があります。 受信アラートの量に合うのは、圧倒的な可能性があります。 これらのタスクの一部を自動化すると役立ちます。

AIR を使用すると、セキュリティ運用チームは、より効率的かつ効果的に運用できます。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に効果的に対応できます。 AIR を使用すると、セキュリティ運用チームは、トリガーされる重要なアラートを見失わずに優先度の高いタスクに集中できます。

この記事の内容

- [AIR の全体的な流れ](#the-overall-flow-of-air)。
- [AIR を取得する方法](#how-to-get-air)。そして
- AIR [機能を構成または](#required-permissions-to-use-air-capabilities) 使用するために必要なアクセス許可。
- 新しいポータルに近日公開されるMicrosoft 365 Defender変更

この記事には、次 [の手順と](#next-steps)、詳細を確認するためのリソースも含まれています。

## <a name="the-overall-flow-of-air"></a>AIR の全体的な流れ

アラートがトリガーされ、セキュリティ プレイブックが自動調査を開始し、結果と推奨されるアクションが発生します。 次に、AIR の全体的なフローをステップバイ ステップで示します。

1. 自動調査は、次のいずれかの方法で開始されます。
   - 電子 [メールで疑](#which-alert-policies-trigger-automated-investigations) わしい何か (メッセージ、添付ファイル、URL、侵害されたユーザー アカウントなど) によってアラートがトリガーされます。 インシデントが作成され、自動調査が開始されます。または
   - セキュリティ アナリストは、 [エクスプローラーの使用中に自動](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) 調査を開始 [します](threat-explorer.md)。
2. 自動調査の実行中に、問題の電子メールと、その電子メールに関連するエンティティに関するデータを収集します。 このようなエンティティには、ファイル、URL、受信者を含めることもできます。 新しいアラートと関連するアラートがトリガーされると、調査の範囲が増える可能性があります。
3. 自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には [、検出された](air-remediation-actions.md) 脅威に対応して修復するために実行できる推奨アクションが含まれます。
4. セキュリティ運用チームは、 [調査結果と](air-view-investigation-results.md)推奨事項を確認し、修復アクションを承認または [拒否します](air-review-approve-pending-completed-actions.md)。
5. 保留中の修復アクションが承認 (または拒否) されると、自動調査が完了します。

Microsoft Defender for Office 365修復アクションは自動的に実行されません。 修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。 AIR 機能は、修復アクションを特定し、情報に基づいた意思決定に必要な詳細を提供することで、セキュリティ運用チームの時間を節約します。

各自動調査の間と後に、セキュリティ運用チームは次の操作を実行できます。

- [調査に関連するアラートの詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)
- [調査の結果としてアクションを確認および承認する](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 詳細な概要については、「 [AIR のしくみ」を参照してください](automated-investigation-response-office.md)。

## <a name="how-to-get-air"></a>AIR の入手方法

ポリシーとアラートが構成されている場合、AIR 機能は [Microsoft Defender](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) Office 365に含まれています。 いくつかのヘルプが必要ですか? 「脅威から保護 [する」のガイダンスに](protect-against-threats.md) 従って、次の保護設定を設定または構成します。

- [監査ログ](../../compliance/turn-audit-log-search-on-or-off.md) (有効にする必要があります)
- [マルウェア対策保護](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [フィッシング対策保護](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)
- [スパム対策保護](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [セーフリンクと添付ファイルセーフリンク](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

さらに、組織のアラート [ポリシー](../../compliance/alert-policies.md) 、特に脅威管理カテゴリの既定のポリシーを確認 [してください](../../compliance/alert-policies.md#default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>自動調査をトリガーするアラート ポリシー

Microsoft 365には、Exchange 管理者アクセス許可の悪用、マルウェアアクティビティ、外部および内部の潜在的な脅威、情報ガバナンスのリスクを特定するのに役立つ、多くの組み込みのアラート ポリシーが提供されています。 既定のアラート [ポリシーのいくつかは、](../../compliance/alert-policies.md#default-alert-policies) 自動調査をトリガーできます。 次の表では、自動調査をトリガーするアラート、Microsoft 365 Defender ポータルでの重大度、および生成方法について説明します。

|通知|重要度|アラートの生成方法|
|---|---|---|
|悪意のある可能性がある URL のクリックが検出されました|**High**|このアラートは、次の場合に生成されます。 <ul><li>組織のリンクで保護[セーフユーザー](safe-links.md)が悪意のあるリンクをクリックする</li><li>URL の評決の変更は、Microsoft Defender によって特定Office 365</li><li>ユーザーは、セーフリンクの警告ページを上書きします (組織の [リンク] セーフ[に基づく](set-up-safe-links-policies.md))。</li></ul> <p> このアラートをトリガーするイベントの詳細については、「[Set up セーフリンク ポリシー」を参照してください](set-up-safe-links-policies.md)。|
|電子メール メッセージがマルウェアまたはフィッシングとしてユーザーによって報告される|**情報**|このアラートは、組織のユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用[](enable-the-report-message-add-in.md)してフィッシングメールとしてメッセージを[報告するときに生成されます](enable-the-report-phish-add-in.md)。|
|配信後にマルウェアを含む電子メール メッセージが削除される|**情報**|このアラートは、マルウェアを含む電子メール メッセージが組織内のメールボックスに配信されると生成されます。 このイベントが発生した場合、Microsoft はゼロ時間自動削除 [(ZAP)](zero-hour-auto-purge.md) を使用して、Exchange Onlineメールボックスから感染したメッセージを削除します。|
|配信後にフィッシング URL を含む電子メール メッセージが削除される|**情報**|このアラートは、フィッシングを含むメッセージが組織内のメールボックスに配信されると生成されます。 このイベントが発生した場合、Microsoft は ZAP を使用して、感染Exchange Onlineメールボックス[から削除します](zero-hour-auto-purge.md)。|
|不審なメール送信パターンが検出される|**Medium**|このアラートは、組織内の誰かが不審なメールを送信し、電子メールの送信を制限される危険性がある場合に生成されます。 このアラートは、アカウントが侵害されたが、ユーザーを制限するのに十分な重大性を示す可能性がある動作に関する早期の警告です。 <p> まれですが、このポリシーによって生成されるアラートは異常である可能性があります。 ただし、ユーザー アカウントが侵害されているかどうかを確認 [するとよいでしょう](responding-to-a-compromised-email-account.md)。|
|ユーザーが電子メールの送信を制限されている|**High**|このアラートは、組織内のユーザーが送信メールの送信を制限されている場合に生成されます。 通常、このアラートはメール アカウントが [侵害された場合に発生します](responding-to-a-compromised-email-account.md)。 <p> 制限付きユーザーの詳細については、「[制限](removing-user-from-restricted-users-portal-after-spam.md)付きユーザーポータルからブロックされたユーザーを削除する」を参照Microsoft 365。|

> [!TIP]
> アラート ポリシーの詳細や既定の設定の編集については、「アラート ポリシー」を参照[Microsoft 365 コンプライアンス センター。](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 機能を使用するために必要なアクセス許可

アクセス許可は、次の表に示す役割など、特定の役割を通じて付与されます。

|タスク|必要な役割|
|---|---|
|AIR 機能のセットアップ|次のいずれかの役割。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li></ul> <p> これらの役割は、[ユーザーまたはAzure Active Directory](/azure/active-directory/roles/permissions-reference)ポータル[で割りMicrosoft 365 Defenderできます](permissions-microsoft-365-security-center.md)。|
|自動調査の開始 <p> --- または --- <p> 推奨されるアクションを承認または拒否する|次のいずれかの役割 (このロールは、[Azure Active Directoryポータル](/azure/active-directory/roles/permissions-reference)[で割りMicrosoft 365 Defenderされます](permissions-microsoft-365-security-center.md)。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li><li>セキュリティ オペレーター</li><li>セキュリティ閲覧者 <br> --- さらに --- </li><li>検索と削除 (この役割は、ポータルのMicrosoft 365 Defender[されます](permissions-microsoft-365-security-center.md)。 新しいメール グループを作成し、&グループに検索役割と削除役割を追加する必要があります。</li></ul>|

## <a name="required-licenses"></a>必須のライセンス

[Microsoft Defender for Office 365プラン 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) ライセンスを割り当てる必要があります。

- セキュリティ管理者 (グローバル管理者を含む)
- 組織のセキュリティ操作チーム (セキュリティ リーダーと検索と削除の役割を持 **つユーザーを含** む)
- エンド ユーザー

## <a name="changes-are-coming-soon-in-your-microsoft-365-defender-portal"></a>変更は、新しいポータルMicrosoft 365 Defender予定です

Microsoft Defender で既に AIR 機能を使用している場合は、Office 365ポータルでいくつかの変更点を確認[Microsoft 365 Defenderしています](../defender/microsoft-365-defender.md#the-microsoft-365-defender-portal)。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="統合アクション センター。":::

新しく改善されたMicrosoft 365 Defenderポータル<https://security.microsoft.com>には、[Microsoft Defender for microsoft Defender と Microsoft Defender](defender-for-office-365.md) [for Endpoint Office 365 AIR 機能が統合されています](../defender-endpoint/automated-investigations.md)。 これらの更新プログラムと改善により、セキュリティ運用チームは、メール、共同作業のコンテンツ、ユーザー アカウント、デバイスに対する自動調査と修復処理に関する詳細を 1 か所で確認できます。

> [!TIP]
> 新しい管理Microsoft 365 Defenderは、次の管理センターに置き換まれます。
>
> - セキュリティ & コンプライアンス センター (<https://protection.office.com>)
> - Microsoft 365 Defender (<https://security.microsoft.com>)
>
> URL の変更に加えて、セキュリティ チームにより合理化されたエクスペリエンスを提供するように設計された新しい外観が提供され、1 か所で脅威検出が多く表示されます。

### <a name="what-to-expect"></a>想定される変化

次の表に、Microsoft Defender の AIR に加わる変更と改善点を示Office 365。

|項目|何が変わるのか?|
|---|---|
|**[調査]** ページ|更新された [ **調査] ページ** は、 [Microsoft Defender for Endpoint に表示される情報とより一貫性があります](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)。 統合された新しい [調査] ビューに合わせて、一般的な形式とスタイルの変更 **が表示** されます。 たとえば、調査グラフの形式が統一されています。|
|**[ユーザー]** タブ|[ **ユーザー]** タブが [ **メールボックス] タブ** です。ユーザーに関する詳細は、[メールボックス] タブ **に表示** されます。|
|**[メール]** タブ|[ **メール]** タブが削除されました。[エンティティ] **タブにアクセス** して、電子メールおよび電子メール クラスターアイテムの一覧を表示します。|
|**[エンティティ]** タブ|[ **エンティティ] タブ** には、すべての概要ビューを含むタブインタブ スタイルと、エンティティの種類別にフィルター処理する機能があります。 [ **エンティティ] タブには** 、[ **エクスプローラーで開** く] オプションに加えて、Go **ハンティング オプションが追加** されています。 エクスプローラーまたは高度な検索[を](threat-explorer.md)[使用して](../defender-endpoint/advanced-hunting-overview.md)エンティティと脅威を検索し、結果をフィルター処理できます。|
|**[アクション]** タブ|更新された [ **アクション] タブ** には、[ **保留中** のアクション] タブと [アクションの履歴] **タブが追加** されました。保留中のアクションを選択すると表示されるサイド ウィンドウで、アクションを承認 (または拒否) できます。|
|**[証拠]** タブ|新しい **[証拠]** タブには、アクションに関連する主要なエンティティの結果が表示されます。 各証拠に関連するアクションは、保留中のアクションを選択するときに開くサイド ウィンドウで承認 (または拒否) できます。|
|**アクション センター**|更新されたアクション **センター** (<https://security.microsoft.com/action-center>) は、電子メール、デバイス、および ID 間で保留中のアクションと完了したアクションをまとめます。 詳細については、「アクション センター」を参照してください。 (詳細については、「アクション センター [」を参照](../defender/m365d-action-center.md)してください。|
|**[インシデント]** ページ|[ **インシデント] ページ** では、複数の調査を相互に関連付け、調査の統合されたビューを向上しました。 ([インシデントの詳細については、次を参照](../defender/incidents-overview.md)してください)。|

## <a name="next-steps"></a>次の手順

- [自動調査の詳細と結果を確認する](air-view-investigation-results.md#view-details-of-an-investigation)
- [保留中のアクションの確認と承認](air-remediation-actions.md)
