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
ms.openlocfilehash: d777ca0a61655c8df16d62c72691195bdec330a9
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175781"
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