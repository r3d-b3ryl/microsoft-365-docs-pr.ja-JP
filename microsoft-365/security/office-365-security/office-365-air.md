---
title: Office 365 の自動調査と応答
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
ms.openlocfilehash: 7bfa07880a302f77769ee15e9108db21dac2519c
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228572"
---
# <a name="office-365-automated-investigation-and-response"></a>Office 365 の自動調査と応答

[Office 365 Advanced Threat Protection](office-365-atp.md)Plan 2 には、セキュリティ運用チームの時間と労力を節約できる強力な自動化された調査と応答 (AIR) 機能が含まれています。 特定のアラートがトリガーされると、1つ以上のセキュリティプレイブックが開始され、自動調査プロセスが開始されます。 これにより、セキュリティ運用チームが、トリガーされた通知を失うことなく、優先度の高いタスクに集中できるようになります。 

AIR の流れは大まかには次のようになります。

|手順  |結果  |
|---------|---------|
|1-d     |通知は Office イベントによってトリガーされ、[セキュリティのプレイブック](automated-investigation-response-office.md#security-playbooks)は選択した通知の自動調査を開始します。 <br/><br/>あるいは、セキュリティアナリストは、[脅威エクスプローラー](threat-explorer.md)を使用して自動化され[た調査を開始](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)することもできます。        |
|pbm-2     |自動調査を実行すると、電子メールとその電子メールに関連するエンティティ (ファイル、Url、受信者) に関する追加データが収集されます。  新しい関連する警告がトリガーされると、調査のスコープが向上する可能性があります。         |
|1/3     |自動調査の実行中および実行後は、[詳細情報と結果](air-view-investigation-results.md)を表示することができます。 結果には、検出された脅威に対処し、修復を行うためにとることができる[推奨処理](air-remediation-actions.md) が含まれます。 また、すべての調査活動を追跡する[プレイブック ログ](air-view-investigation-results.md#playbook-log)が提供されます。<br/><br/>組織でカスタム レポート ソリューションまたはサード パーティのソリューションを使用している場合は、[Office 365 マネージメント アクティビティ API を使用して](air-custom-reporting.md)自動調査と脅威に関する情報を表示することができます。         |
|2/4     |セキュリティ運用チームは、[調査結果と推奨事項](air-view-investigation-results.md)を確認し、[修復アクションを承認](air-remediation-actions.md#approve-or-reject-pending-actions)します。 Office 365 では、アクションは自動的には実行されません。 修復処理は、組織のセキュリティチームによる承認時にのみ行われます。         |

自動化された調査プロセスにおいて、セキュリティチームは次のことを行うことができます。

- [調査に関連する通知の詳細を表示する](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [調査の結果の詳細を表示する](air-view-investigation-results.md#view-details-of-an-investigation)
- [調査の結果としてアクションを確認して承認する](air-remediation-actions.md#approve-or-reject-pending-actions)

詳細については、「[エアのしくみ](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)」を参照してください。

## <a name="how-to-get-air"></a>AIR の入手方法

Office 365 AIR は次のサブスクリプションに含まれています。

- Microsoft 365 E5
- Office 365 E5
- Microsoft Threat Protection
- Office 365 Advanced Threat Protection プラン 2

これらのサブスクリプションのいずれも持っていない場合は、[無料の試用版を開始](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)してください。

利用可能な機能の詳細については、「[Advanced Threat Protection (ATP) の各プランで利用できる機能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

## <a name="required-permissions-to-use-air-capabilities"></a>空気機能を使用するために必要なアクセス許可

アクセス許可は、次の表に記載されているような特定の役割によって付与されます。 

|タスク |必要な役割 |
|--|--|
|エア機能を設定するには |次のいずれかの役割: <br/>- **グローバル管理者**<br/>- **セキュリティ管理者** <br/>これらの役割は、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てることができます。 |
|推奨されるアクションを承認または拒否するには|[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)または[Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)で割り当てられている次のいずれかの役割。<br/>- **グローバル管理者** <br/>- **セキュリティ管理者**<br/>- **セキュリティリーダ** <br/>--- さらに ---<br/>- **検索と削除**(この役割は、 [Office 365 セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)でのみ割り当てられます。 そこで新しい役割グループを作成し、その新しい役割グループに検索役割と削除役割を追加する必要がある場合があります。

## <a name="related-articles"></a>関連記事

- [Microsoft Threat Protection での自動調査および対応](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Microsoft Defender Advanced Threat Protection の自動化された調査と修復](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)