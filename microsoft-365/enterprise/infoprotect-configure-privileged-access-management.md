---
title: '手順 6: Office 365 の特権アクセス管理を構成する'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Office 365 の特権アクセス管理について理解して構成します。
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399951"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a>手順 6: Office 365 の特権アクセス管理を構成する

*この手順はオプションであり、Microsoft 365 Enterprise の E5 および Advanced Compliance バージョンにのみ適用されます。*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

特権アクセス管理は、Office 365 テナントでのタスクベースのアクティビティに対して Just-In-Time アクセスを指定するポリシーを構成することで有効になります。これは、機密性の高いデータへの継続的なアクセスや重要な構成設定へのアクセスに、既存の特権管理者アカウントが使用される可能性のある侵害から組織を保護するために役立ちます。たとえば、Office 365 テナント内の組織のメールボックス設定にアクセスして変更する際には、明示的な承認が必要になる特権アクセス管理ポリシーを構成できます。

この手順では、Office 365 テナントの特権アクセス管理を有効にして、組織の Office 365 データおよび構成設定へのタスクベースのアクセスに対するセキュリティを強化する特権アクセスポリシーを構成します。Office 365 組織の特権アクセスは、次の 3 つの基本的な手順で開始します。
- 承認者のグループを作成する
- 特権アクセスを有効にする
- 承認ポリシーを作成する

構成が完了すると、特権アクセス管理によって、継続的な特権なしで運用できるようになり、継続的な管理アクセスが原因で発生する脆弱性に対抗する防御層が得られます。定義済みの承認ポリシーが関連付けられているタスクを特権アクセスで実行するには、承認が必要になります。承認ポリシーに含まれているタスクの実行を必要とするユーザーは、そのポリシーで定義されているタスクの実行に必要なアクセス許可を得るために、アクセス承認を要求して承認される必要があります。

Office 365 の特権アクセス管理を有効にするには、「[Office 365 の特権アクセス管理を構成する](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)」のトピックを参照してください。

詳細については、「[Office 365 の特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」のトピックを参照してください。

## <a name="results"></a>結果

この手順の結果、組織にとって重要なデータと構成設定に対する Just-In-Time アクセス制御が有効になり、Office 365 のセキュリティが向上しました。

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step6)を確認してください。

## <a name="next-step"></a>次の手順

[情報保護インフラストラクチャの終了条件](infoprotect-exit-criteria.md)