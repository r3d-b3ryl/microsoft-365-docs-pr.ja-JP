---
title: アプリに対するユーザーの同意を管理Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: アプリに対するユーザーの同意、およびアプリを有効にし、サード パーティ製アプリがユーザーの情報にアクセスMicrosoft 365します。
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391233"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>アプリに対するユーザーの同意を管理Microsoft 365

この設定は、ユーザーがサインインおよびデータへのアクセス要求に OpenID Connect および OAuth 2.0 を使用するアプリに対してその同意を与えるかどうかを制御します。 アプリは、自分の組織内から作成するか、別の組織またはOffice 365から作成できます。

この設定を有効にすると、これらのアプリはユーザーに組織のデータへのアクセス許可を求め、ユーザーは許可するかどうかを選択できます。 この設定をオフにした場合、管理者はユーザーがアプリを使用する前に、それらのアプリに同意する必要があります。 この場合は、ユーザーがブロックされたアプリを使用する管理者の承認要求を送信できるよう、Azure portal で管理者の同意ワークフローを設定する方法を検討してください。

ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。 他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。

## <a name="turning-user-consent-on-or-off"></a>ユーザーの同意をオンまたはオフにする

アプリに対するユーザーの同意を有効またはオフにする方法を次に示します。

1. 管理センターで、[組織の設定サービス]**ページ設定** に移動し、[アプリに対するユーザーの同意 \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743)**] を選択します**。

2. [アプリ **に対するユーザーの同意** ] ページで、ユーザーの同意を有効または無効にするオプションを選択します。

## <a name="related-content"></a>関連コンテンツ 

[管理者の同意ワークフローを構成](/azure/active-directory/manage-apps/configure-admin-consent-workflow) する (記事)\
[アプリケーションへの同意の管理と同意要求の評価](/azure/active-directory/manage-apps/manage-consent-requests) (記事)