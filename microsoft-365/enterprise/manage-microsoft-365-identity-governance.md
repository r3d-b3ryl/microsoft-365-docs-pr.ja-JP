---
title: Microsoft 365 ID ガバナンスを管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 ID ガバナンス機能を使用する方法について説明します。
ms.openlocfilehash: 4b24ec8b68763689ee073821a4a638c196b98c9b
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67343111"
---
# <a name="manage-microsoft-365-identity-governance"></a>Microsoft 365 ID ガバナンスを管理する

Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。 たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。

詳細については、 [Azure Active Directory (Azure AD) の ID ガバナンスの概要](/azure/active-directory/governance/identity-governance-overview)を参照してください。

## <a name="set-up-azure-ad-access-reviews"></a>Azure AD アクセス レビューを設定する

Azure AD アクセス レビューを使用すると、ユーザーのアクセス権を確認して、適切なユーザーのみが継続的にアクセスできることを確認できます。 例:

- 新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。
- 従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。
- 従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。

これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。

詳細については、 [アクセス レビューの概要](/azure/active-directory/governance/access-reviews-overview)を参照してください。

さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。

- [グループとアプリ](/azure/active-directory/governance/create-access-review)
- [Azure AD ロール](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure リソース ロール](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Azure AD エンタイトルメント管理を設定する

Azure AD エンタイトルメント管理を使用すると、アクセス要求ワークフロー、アクセス割り当て、レビュー、有効期限を自動化することで、ID とアクセスのライフサイクルを大規模に管理できます。

従業員は、ジョブを実行するために、さまざまなグループ、アプリケーション、サイトにアクセスする必要があります。 要件が変更されたり、新しいアプリケーションが追加されたり、ユーザーが追加のアクセス権を必要としたりするため、このアクセスの管理は困難になる可能性があります。 他の組織と共同作業を行う場合、他の組織の誰が組織のリソースにアクセスする必要があるかがわからない場合があります。外部のユーザーは、組織が使用しているアプリケーション、グループ、またはサイトを知りません。

Azure AD エンタイトルメント管理は、グループ、アプリケーション、SharePoint サイトへのアクセスをより効率的に管理し、内部および外部のユーザーに提供するのに役立ちます。
 
詳細については、 [Azure AD エンタイトルメント管理の概要](/azure/active-directory/governance/entitlement-management-overview)を参照してください。
