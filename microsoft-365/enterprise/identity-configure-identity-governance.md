---
title: '手順 7: Identity Governance を構成する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD テナントの Identity Governance を理解し、構成します。
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067354"
---
# <a name="step-6-configure-identity-governance"></a>手順 6: Identity Governance を構成する

![フェーズ 2 - ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。 たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。

Azure Active Directory (Azure AD) のIdentity Governance の詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)を参照してください。


*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Azure AD アクセス レビューを設定する

*これはオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます*

この手順では、Azure AD アクセス レビューを設定します。これにより、ユーザーのアクセスを確認し、適切なユーザーのみが引き続きアクセスできるようにすることができます。 例:

- 新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。
- 従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。
- 従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。

これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。

Azure AD アクセス レビューの詳細については、[この記事](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)を参照してください。

Azure AD Privileged Identity Management (PIM) により、Azure AD、Azure、およびその他の Microsoft クラウド サービスの全体で、リソースに対するアクセス権のセキュリティ保護に合わせた管理を追加することができます。 Azure AD PIM には、会社のリソース (ディレクトリ、Office 365、Azure リソースの役割など) のセキュリティを確保するために、包括的なガバナンス管理のセットが用意されています。 他のアクセス方法と同様、組織では、アクセス レビューを使用して、管理者の役割に属するすべてのユーザーの定期的なアクセス再認定を構成できます。 Azure AD PIM は、Microsoft 365 Enterprise の E5 バージョンでのみ使用できます。

さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。

- [グループとアプリ](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD ロール](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure リソースの役割](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

中間チェックポイントとして、このセクションの[終了条件](identity-exit-criteria.md#crit-identity-access-reviews)を確認できます。

## <a name="next-step"></a>次の手順

[ID インフラストラクチャの終了条件](identity-exit-criteria.md)

