---
title: Microsoft Defender for Office 365 の自動調査と応答の概要
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Office 365 の Microsoft Defender で自動調査および応答機能の使用を開始します。
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925606"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Office 365 の Microsoft Defender で自動調査と応答 (AIR) の使用を開始する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender For Office 365 に](office-365-atp.md) は、セキュリティ運用チームの時間と労力を節約できる強力な自動化された調査および応答 (AIR) 機能が含まれています。 アラートがトリガーされると、その通知をレビュー、優先度設定、応答するためのセキュリティ運用チームが必要になります。 受信通知の音量を維持することは非常に困難です。 これらのタスクの一部を自動化することができます。 AIR を使用すれば、セキュリティ運用チームは、トリガーされる重要な警告を見失うことなく、優先度の高いタスクに集中できます。

この記事の内容
- [空気の全体的な流れ](#the-overall-flow-of-air)。
- [エアを入手する方法](#how-to-get-air)そして 
- AIR 機能を構成または使用するために [必要なアクセス許可](#required-permissions-to-use-air-capabilities) 。 

## <a name="the-overall-flow-of-air"></a>AIR の全体的な流れ

アラートがトリガーされ、セキュリティのプレイブックが自動調査を開始します。これにより、調査結果と推奨される処置が行われます。 エアフローの全体的な流れについては、次の手順を参照してください。

1. 自動調査は、次のいずれかの方法で開始されます。

   - [警告](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)は、電子メール内の疑わしいもの (メッセージ、添付ファイル、URL など) によってトリガーされます。 インシデントが作成されます。 インシデントの種類に応じて、 [セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks) が実行され、自動調査が開始されます。 

     --- または ---
   
   - セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して、自動化された[調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)します。

2. 自動化された調査を実行している間は、問題の電子メールとその電子メールに関連するエンティティに関する追加のデータが収集されます。 このようなエンティティには、ファイル、Url、受信者を含めることができます。  調査の範囲は、新しい通知および関連するアラートがトリガーされると増加することがあります。

3. 自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には、検出された脅威に対応して修復するために実行できる [推奨アクション](air-remediation-actions.md) が含まれます。 また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。


4. セキュリティ運用チームは、 [調査結果と推奨事項](air-view-investigation-results.md)を確認し、 [修復処置を承認または拒否](air-review-approve-pending-completed-actions.md)します。 

5. 保留中の修復操作が承認 (却下) されると、自動調査が完了します。

> [!IMPORTANT]
> Microsoft Defender for Office 365 では、修復アクションは自動的には実行されません。 修復処理は、組織のセキュリティ チームが承認した場合にのみ実行されます。 ただし、空気機能は、修復アクションを識別し、情報に基づいた意思決定を行うために必要な詳細情報を提供することによって、セキュリティ運用チームの時間を節約します。

自動化された各調査の間およびセキュリティ運用チームは、次のことを行うことができます。

- [調査に関連する通知の詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)

- [調査の結果としてアクションを確認して承認する](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 詳細については、「 [航空のしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。

## <a name="how-to-get-air"></a>AIR の入手方法

ポリシーとアラートが構成されている場合は、 [Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)に AIR 機能が含まれています。 この点については、「 [脅威から保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) する」のガイダンスに従って、以下の保護設定をセットアップまたは構成してください。 

1. [監査ログ](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (有効にする必要があります)

2. [マルウェア対策ポリシー](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [フィッシング対策保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [スパム対策の保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection)。
   
5. [安全なリンクと安全な添付ファイル](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)。
   
6. [SharePoint、OneDrive、Microsoft Teams の安全な添付ファイル](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)。
   
7. [電子メールのゼロ時間自動削除](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop)。

さらに、 [組織のアラートポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)、特に [脅威管理カテゴリの既定のポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)を確認してください。 

## <a name="which-alert-policies-trigger-automated-investigations"></a>自動調査をトリガーするアラートポリシーはどれですか。

Microsoft 365 には、Exchange 管理者のアクセス許可の悪用、マルウェアのアクティビティ、外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込み通知ポリシーが用意されています。 [既定の通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)のいくつかでは、自動調査をトリガーできます。 これらには次のコマンドレットがあります。

- 悪意のある可能性がある URL のクリックが検出される
- ユーザーが電子メールメッセージをフィッシングとして報告する
- 配信後にマルウェアを含む電子メールメッセージが削除される
- 配信後にフィッシング Url を含む電子メールメッセージが削除される
- 疑わしい電子メール送信パターンが検出される
- ユーザーが電子メールの送信を制限されている

## <a name="required-permissions-to-use-air-capabilities"></a>空気機能を使用するために必要なアクセス許可

アクセス許可は、次の表に記載されているような特定の役割によって付与されます。 

|タスク |必要な役割 |
|--|--|
|エア機能を設定するには |次のいずれかの役割: <br/>-全体管理者<br/>-セキュリティ管理者 <br/>これらのロールは、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) または [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てることができます。 |
|推奨されるアクションを承認または拒否するには|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てられている次のいずれかの役割。<br/>-全体管理者 <br/>-セキュリティ管理者<br/>-セキュリティリーダ <br/>--- さらに ---<br/>-検索と削除 (この役割は [セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)のみで割り当てられます。 そこで新しい役割グループを作成し、その新しい役割グループに検索役割と削除役割を追加する必要がある場合があります。

## <a name="required-licenses"></a>必要なライセンス

[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ライセンスは次のものに割り当てる必要があります。
- セキュリティ管理者 (全体管理者を含む)
- 組織のセキュリティ運用チーム (セキュリティ閲覧者と、検索と削除の役割を含む)
- エンド ユーザー


## <a name="next-steps"></a>次の手順

- [自動化された調査の詳細と結果を参照する](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [保留中のアクションを確認して承認する](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>関連記事

- [エンドポイントの Microsoft Defender での自動化された調査と修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft 365 Defender での自動調査と応答](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
