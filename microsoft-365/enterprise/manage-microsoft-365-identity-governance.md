---
title: ID ガバナンスMicrosoft 365管理する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
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
description: ID ガバナンス機能を使用するMicrosoft 365について説明します。
ms.openlocfilehash: 35b2092412ddbeacd5d6962e110de1931b2d0f4b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150752"
---
# <a name="manage-microsoft-365-identity-governance"></a>ID ガバナンスMicrosoft 365管理する

Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。 たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。

詳細については、「この概要の ID[ガバナンス for Azure Active Directory (Azure AD) 」を参照してください](/azure/active-directory/governance/identity-governance-overview)。

## <a name="set-up-azure-ad-access-reviews"></a>Azure AD アクセス レビューを設定する

Azure ADアクセス レビューを使用すると、ユーザーのアクセスを確認して、適切なユーザーだけがアクセスを継続するようにすることができます。 例:

- 新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。
- 従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。
- 従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。

これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。

詳細については、「アクセス レビューの [概要」を参照してください](/azure/active-directory/governance/access-reviews-overview)。

さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。

- [グループとアプリ](/azure/active-directory/governance/create-access-review)
- [Azure AD ロール](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure リソース ロール](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Azure のライセンスADを設定する

Wiht Azure AD、アクセス要求ワークフロー、アクセス割り当て、レビュー、有効期限を自動化することで、ID とアクセス ライフサイクルを大規模に管理できます。

従業員は、自分の仕事を実行するために、さまざまなグループ、アプリケーション、およびサイトにアクセスする必要があります。 このアクセスの管理は、要件の変更、新しいアプリケーションの追加、またはユーザーが追加のアクセス権を必要とするために困難な場合があります。 他の組織と共同作業を行う場合、他の組織の誰が組織のリソースにアクセスする必要があるのか分からなかったり、外部のユーザーは組織が使用しているアプリケーション、グループ、またはサイトを知らない場合があります。

Azure ADエンタイトルメント管理を使用すると、グループ、アプリケーション、および内部および外部のユーザー SharePointサイトへのアクセスを効率的に管理できます。
 
詳細については、「Azure の権利管理 [の概要」AD参照してください](/azure/active-directory/governance/entitlement-management-overview)。