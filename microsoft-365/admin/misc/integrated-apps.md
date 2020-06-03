---
title: Microsoft 365 でのアプリへのユーザーの同意の管理
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: アプリに対するユーザーの同意と、サードパーティ製アプリがユーザーの Microsoft 365 情報にアクセスできるようにする方法について説明します。
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498319"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Microsoft 365 でのアプリへのユーザーの同意の管理

この設定では、サインインおよびデータアクセスの要求に対して、OpenID Connect と OAuth 2.0 を使用するアプリに対してユーザーが同意を得ることができるかどうかを制御します。 アプリは、自分の組織内から作成することも、別の Office 365 組織またはサードパーティから入手することもできます。

この設定をオンにすると、これらのアプリは組織のデータへのアクセス許可をユーザーに要求し、許可するかどうかをユーザーが選択できるようにします。 この設定をオフにすると、管理者は、ユーザーが使用できるようにする前に、これらのアプリに同意する必要があります。 この場合は、Azure ポータルで管理者の同意ワークフローを設定し、ブロックされたアプリを使用するためにユーザーが管理者の承認要求を送信できるようにすることを検討してください。

ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。 他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。

## <a name="turning-user-consent-on-or-off"></a>ユーザーの同意を有効または無効にする
<a name="__toc379982114"> </a>

アプリに対するユーザーの同意を有効または無効にする方法は次のとおりです。

1. 管理センターで、[設定] [ **Settings** \> **組織設定**  >  [サービス](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページに移動し、[**アプリへのユーザーの同意**] を選択します。

2. [**アプリへのユーザーの同意**] ページで、[ユーザーの同意を有効または無効にする] オプションを選択します。

## <a name="more-info"></a>詳細情報
<a name="__toc379982114"> </a>

Azure active directory で同意設定を構成する方法については、「[管理者の同意ワークフローを構成](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)する」を参照してください。

ユーザーの同意をアプリに対して管理する方法については、「[アプリケーションの同意を管理する」および「同意要求を評価](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)する」を参照してください。