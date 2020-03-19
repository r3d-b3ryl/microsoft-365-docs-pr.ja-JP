---
title: Office 365 での自動調査および対応 (AIR)
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の使用を開始します。
ms.custom: air
ms.openlocfilehash: 45a2bc0e581916493a0170a5f86c152d02403efe
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826351"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Office 365 での自動調査および対応 (AIR)

[Office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) Plan 2 には、強力な自動化された調査と応答 (航空) 機能が含まれており、セキュリティ運用チームの時間と労力を節約できます。 アラートがトリガーされると、その通知をレビュー、優先度設定、応答するためのセキュリティ運用チームが必要になります。 受信通知の音量を維持することは非常に困難です。 これを自動化することによって役立つことがあります。 AIR を使用すると、セキュリティ運用チームは、トリガーされた通知を失うことなく、優先度の高いタスクに集中できます。

この記事では、空気の[全体的な流れ](#the-overall-flow-of-air)、空気を[取得する方法](#how-to-get-air)、および航空機能を構成または使用するために[必要なアクセス許可](#required-permissions-to-use-air-capabilities)について説明します。 

## <a name="the-overall-flow-of-air"></a>AIR の全体的な流れ

高いレベルでは、アラートがトリガーされ、セキュリティによるプレイの開始と自動化された調査が行われて、結果と推奨事項が得られます。 エアフローの全体的な流れについては、次の手順を参照してください。

1. 自動調査は、次のいずれかの方法で開始されます。

   - [通知](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)は Office イベントによってトリガーされ、インシデントを作成します。 インシデントの種類に応じて、[セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks)が自動調査を開始します。 

     --- または ---
   
   - セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して、自動化された[調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)します。

2. 自動化された調査を実行している間は、問題の電子メールとその電子メールに関連するエンティティに関する追加のデータが収集されます。 このようなエンティティには、ファイル、Url、受信者を含めることができます。  調査の範囲は、新しい通知および関連するアラートがトリガーされると増加することがあります。

3. 自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には、検出された脅威に対処し、修復を行うためにとることができる[推奨処理](air-remediation-actions.md) が含まれます。 また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。

    組織でカスタム レポート ソリューションまたはサード パーティのソリューションを使用している場合は、[Office 365 マネージメント アクティビティ API を使用して](air-custom-reporting.md)自動調査と脅威に関する情報を表示することができます。

4. セキュリティ運用チームは、[調査結果と推奨事項](air-view-investigation-results.md)を確認し、[修復処置を承認または拒否](air-review-approve-pending-completed-actions.md)します。 

    保留中の修復操作が承認 (却下) されると、自動調査が完了します。

> [!NOTE]
> Office 365 ATP では、修復アクションは自動的には実行されません。 修復処理は、組織のセキュリティチームによる承認時にのみ行われます。 

自動化された調査プロセスにおいて、セキュリティチームは次のことを行うことができます。

- [調査に関連する通知の詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)

- [調査の結果としてアクションを確認して承認する](air-review-approve-pending-completed-actions.md)

> [!TIP]
> 詳細については、「[エアのしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。

## <a name="how-to-get-air"></a>AIR の入手方法

Office 365 の航空機能は、 [office 365 Advanced Threat Protection プラン 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)に含まれています。 ただし、Office 365 の ATP ポリシーは、エアが期待どおりに動作するように[構成する必要があり](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)ます。 さらに、組織の[通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)を確認し、必要に応じて構成する必要があります。 

Office 365 には、Exchange 管理者のアクセス許可の悪用、マルウェアのアクティビティ、外部および内部の脅威、および情報ガバナンスのリスクを特定するのに役立つ、多くの組み込み通知ポリシーが用意されています。 [既定の通知ポリシー](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)のいくつかでは、自動調査をトリガーできます。 これらには次のコマンドレットがあります。

- 悪意のある可能性がある URL のクリックが検出される

- ユーザーが電子メールメッセージをフィッシングとして報告する

- 配信後にマルウェアを含む電子メールメッセージが削除される

- 配信後にフィッシング Url を含む電子メールメッセージが削除される

- 疑わしい電子メール送信パターンが検出される

- ユーザーが電子メールの送信を制限されている

[通知とエアの詳細について説明](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)します。

## <a name="required-permissions-to-use-air-capabilities"></a>空気機能を使用するために必要なアクセス許可

アクセス許可は、次の表に記載されているような特定の役割によって付与されます。 

|タスク |必要な役割 |
|--|--|
|エア機能を設定するには |次のいずれかの役割: <br/>-全体管理者<br/>-セキュリティ管理者 <br/>これらの役割は、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てることができます。 |
|推奨されるアクションを承認または拒否するには|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てられている次のいずれかの役割。<br/>-全体管理者 <br/>-セキュリティ管理者<br/>-セキュリティリーダ <br/>--- さらに ---<br/>-検索と削除 (この役割は、 [Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)でのみ割り当てられます。 そこで新しい役割グループを作成し、その新しい役割グループに検索役割と削除役割を追加する必要がある場合があります。

## <a name="next-steps"></a>次の手順

- [自動化された調査の詳細と結果を参照する](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [保留中のアクションを確認して承認する](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>関連記事

- [Microsoft Defender Advanced Threat Protection の自動化された調査と修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Microsoft Threat Protection での自動調査および対応](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
