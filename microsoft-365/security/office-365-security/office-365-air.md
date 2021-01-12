---
title: Microsoft Defender for Office 365 での自動調査と対応
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 の自動調査および対応機能の使用を開始します。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 6ccefb5c435f08fcef4dcc872af676fba70668ee
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794546"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Microsoft Defender での自動調査と対応 (AIR) for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender for Office 365](office-365-atp.md) には、セキュリティ運用チームの時間と労力を節約できる強力な自動調査および対応 (AIR) 機能が含まれています。 アラートがトリガーされると、セキュリティ運用チームがそれらのアラートを確認、優先順位付け、対応する必要があります。 受信通知の量に関する情報は、大き過大になる可能性があります。 これらのタスクの一部を自動化すると役立ちます。

AIR を使用すると、セキュリティ運用チームが効率的かつ効果的に運用できます。 AIR 機能には、現在存在する既知の脅威に対応する自動調査プロセスが含まれます。 適切な修復アクションは承認を待ち、セキュリティ運用チームが検出された脅威に効果的に対応できます。 AIR を使用すると、セキュリティ運用チームは、トリガーされる重要なアラートを見失わずに、優先度の高いタスクに集中できます。

この記事の内容

- [AIR の全体的な流れ](#the-overall-flow-of-air)。
- [AIR を取得する方法](#how-to-get-air)そして
- AIR [機能を構成または](#required-permissions-to-use-air-capabilities) 使用するために必要なアクセス許可。

この記事には、次 [の手順と](#next-steps)詳細を確認するためのリソースも含まれています。

## <a name="the-overall-flow-of-air"></a>AIR の全体的な流れ

アラートがトリガーされ、セキュリティ プレイブックによって自動調査が開始され、結果として結果が見つまり、推奨されるアクションが実行されます。 次に、AIR の全体的なフローをステップ バイ ステップで示します。

1. 自動調査は、次のいずれかの方法で開始されます。

   - 警告 [は、電子メール](#which-alert-policies-trigger-automated-investigations) に不審な情報 (メッセージ、添付ファイル、URL、侵害されたユーザー アカウントなど) によってトリガーされます。 インシデントが作成され、自動調査が開始されます。

     --- または ---

   - セキュリティ アナリストは [、脅威エクスプローラーの使用中](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) に自動調査 [を開始します](threat-explorer.md)。

2. 自動調査を実行すると、該当する電子メールと、その電子メールに関連するエンティティに関する追加データが収集されます。 このようなエンティティには、ファイル、URL、および受信者を含めることもできます。  新しいアラートや関連するアラートがトリガーされると、調査の範囲が広がる可能性があります。

3. 自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には [、検出された](air-remediation-actions.md) 脅威に対応して修復するために実行できる推奨アクションが含まれます。 また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。

4. セキュリティ運用チームは、調査結果 [と推奨事項を](air-view-investigation-results.md)確認し、修復 [アクションを承認または拒否します](air-review-approve-pending-completed-actions.md)。

5. 保留中の修復アクションが承認 (または拒否) されると、自動調査が完了します。

> [!IMPORTANT]
> Microsoft Defender for Office 365 では、修復アクションは自動的に実行されません。 修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。
>
> AIR 機能は、修復アクションを識別し、情報に基づいた意思決定に必要な詳細を提供することで、セキュリティ運用チームの時間を節約します。

自動調査を行うごとに、セキュリティ運用チームは次の操作を実行できます。

- [調査に関連するアラートの詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)

- [調査の結果としてアクションを確認および承認する](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 詳細については [、「AIR](automated-investigation-response-office.md)のしくみ」を参照してください。

## <a name="how-to-get-air"></a>AIR の入手方法

ポリシーとアラートが構成されている場合、AIR 機能は [Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)用の Microsoft Defender に含まれています。 サポートが必要な場合は、「脅威から保護する」の[](protect-against-threats.md)ガイダンスに従って、次の保護設定を設定または構成します。

1. [監査ログ](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (有効にする必要があります)

2. [マルウェア対策ポリシー](protect-against-threats.md#part-1---anti-malware-protection)

3. [アンチフィクション保護](protect-against-threats.md#part-2---anti-phishing-protection)

4. [スパム対策保護](protect-against-threats.md#part-3---anti-spam-protection)。

5. [安全なリンクと安全な添付ファイル](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。

6. [SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。

7. [電子メールのゼロアワー自動消去](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)。

さらに、組織のアラート [ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)、特に脅威管理カテゴリの既定のポリシーを必ず [確認してください](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)。

## <a name="which-alert-policies-trigger-automated-investigations"></a>自動調査をトリガーするアラート ポリシーは何ですか?

Microsoft 365 には、Exchange 管理者のアクセス許可の不正使用、マルウェアアクティビティ、外部および内部の潜在的脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込みのアラート ポリシーが提供されています。 既定のアラート [ポリシーの中には、自動](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) 調査をトリガーできるものがあります。 次の表に、自動調査をトリガーするアラート、Microsoft 365 セキュリティ センターでの重大度、生成方法を示します。

|アラート|重要度|アラートの生成方法|
|---|---|---|
|悪意のある可能性がある URL のクリックが検出されました|**High**|このアラートは、次の場合に生成されます。 <ul><li>組織内の安全なリンク [によって保護](atp-safe-links.md) されているユーザーが悪意のあるリンクをクリックする</li><li>URL の Verdict の変更は、Microsoft Defender によって 365 Office識別されます。</li><li>ユーザーは、安全なリンクに関する警告ページ (組織の安全なリンク ポリシーに基づく) [を上書きします](set-up-atp-safe-links-policies.md)。</li></ul> <p> このアラートをトリガーするイベントの詳細については、「安全なリンク ポリシーの [設定」を参照してください](set-up-atp-safe-links-policies.md)。|
|電子メール メッセージがマルウェアまたはフィッシングとしてユーザーによって報告される|**情報提供**|この警告は、組織内のユーザーがレポート メッセージ アドインを使用してメッセージをフィッシングメールとして [報告すると生成されます](enable-the-report-message-add-in.md)。|
|マルウェアを含む電子メール メッセージが配信後に削除される|**情報提供**|この警告は、マルウェアを含む電子メール メッセージが組織内のメールボックスに配信されると生成されます。 このイベントが発生した場合、Microsoft はゼロアワー自動消去を使用して、感染したメッセージを Exchange Online メールボックス [から削除します](zero-hour-auto-purge.md)。|
|フィッシング URL を含む電子メール メッセージは配信後に削除されます|**情報提供**|この警告は、フィッシングを含むメッセージが組織内のメールボックスに配信されると生成されます。 このイベントが発生した場合、Microsoft はゼロアワー自動消去を使用して Exchange Online メールボックスから感染したメッセージ [を削除します](zero-hour-auto-purge.md)。|
|不審な電子メール送信パターンが検出される|**Medium**|この警告は、組織内の誰かが不審なメールを送信し、電子メールの送信が制限される危険性がある場合に生成されます。 これは、アカウントが侵害されているが、ユーザーを制限するほど重大ではない可能性がある動作に対する早期警告です。 <p> まれですが、このポリシーによって生成されるアラートは異常である可能性があります。 ただし、ユーザー アカウントが侵害されているかどうかを確認する [方が良い方法です](responding-to-a-compromised-email-account.md)。|
|ユーザーがメールの送信を制限されている|**High**|この警告は、組織内のユーザーが送信メールの送信を制限されている場合に生成されます。 これは通常、電子メール アカウント [が侵害された場合に発生します](responding-to-a-compromised-email-account.md)。 <p> 制限されたユーザーの詳細については [、「Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md)の制限付きユーザー ポータルからブロックされたユーザーを削除する」を参照してください。|
|

> [!TIP]
> アラート ポリシーの詳細や既定の設定の編集については [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)コンプライアンス センターのアラート ポリシーを参照してください。

## <a name="required-permissions-to-use-air-capabilities"></a>AIR 機能を使用するために必要なアクセス許可

アクセス許可は、次の表に示すロールなど、特定のロールによって付与されます。

|Task|Role(s) required|
|---|---|
|AIR 機能のセットアップ|次の役割のいずれかを指定します。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li></ul> <p> これらのロールは [、Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) またはセキュリティ/コンプライアンス センター [&割り当てることができます](permissions-in-the-security-and-compliance-center.md)。|
|自動調査を開始する <p> --- または --- <p> 推奨されるアクションを承認または拒否する|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)またはセキュリティ センター コンプライアンス センターで割り当てられる、次[&の 1 つ](permissions-in-the-security-and-compliance-center.md)。 <ul><li>グローバル管理者</li><li>セキュリティ管理者</li><li>セキュリティ閲覧者 <br> --- さらに --- </li><li>検索と消去 (この役割は、セキュリティ/コンプライアンス センター [&割り当てられます](permissions-in-the-security-and-compliance-center.md)。 そこで新しい役割グループを作成し、その新しい役割グループに "Search and Purge/検索と消去" 役割を追加する必要がある場合があります。</li></ul>|
|

## <a name="required-licenses"></a>必要なライセンス

[Microsoft Defender for Office 365 プラン 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) ライセンスを割り当てる必要があります。

- セキュリティ管理者 (グローバル管理者を含む)
- 組織のセキュリティ運用チーム (セキュリティ 閲覧者と検索と消去の役割を持 **つユーザーを含** む)
- エンド ユーザー

## <a name="next-steps"></a>次の手順

- [自動調査の詳細と結果を表示する](air-view-investigation-results.md#view-details-of-an-investigation)

- [保留中のアクションを確認および承認する](air-remediation-actions.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint での自動調査と修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender での自動調査と対応](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
