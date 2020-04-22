---
title: '手順 7: 特権アクセス管理を構成する'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 特権アクセス管理について理解し、構成します。
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636990"
---
# <a name="step-7-configure-privileged-access-management"></a>手順 7: 特権アクセス管理を構成する

*この手順はオプションであり、Microsoft 365 Enterprise の E5 および Advanced Compliance バージョンにのみ適用されます。*

![フェーズ 6: 情報保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

特権アクセス管理は、テナント内のタスクベースのアクティビティに対してジャストインタイムアクセスを指定するポリシーを構成することで有効になります。 機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。 たとえば、テナント内の組織のメールボックスの設定にアクセスして変更するために、明示的な承認を必要とする特権アクセス管理ポリシーを構成することができます。

この手順では、テナントで特権アクセス管理を有効にし、組織のデータおよび構成設定へのタスクベースのアクセスに対して追加のセキュリティを提供する特権アクセスポリシーを構成します。 組織での特権アクセスを開始するには、次の3つの基本的な手順を実行します。
- 承認者のグループを作成する
- 特権アクセスを有効にする
- 承認ポリシーを作成する

構成が完了すると、特権アクセス管理によって、継続的な特権なしで運用できるようになり、継続的な管理アクセスが原因で発生する脆弱性に対抗する防御層が得られます。定義済みの承認ポリシーが関連付けられているタスクを特権アクセスで実行するには、承認が必要になります。承認ポリシーに含まれているタスクの実行を必要とするユーザーは、そのポリシーで定義されているタスクの実行に必要なアクセス許可を得るために、アクセス承認を要求して承認される必要があります。

特権アクセス管理を有効にするには、「[特権アクセス管理を構成](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)する」トピックを参照してください。

詳細については、「[特権アクセス管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」を参照してください。


|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  テスト ラボ環境でこの構成の実習を行うには、「[特権アクセス管理テスト ラボ ガイド](privileged-access-microsoft-365-enterprise-dev-test-environment.md)」を参照してください。 |
|||

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step7)を確認できます。

## <a name="next-step"></a>次の手順

[情報保護インフラストラクチャの終了条件](infoprotect-exit-criteria.md)
