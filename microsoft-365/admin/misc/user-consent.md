---
title: Microsoft 365でアプリに対するユーザーの同意を管理する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: アプリに対するユーザーの同意と、サード パーティ製アプリがユーザーのMicrosoft 365情報にアクセスできるようにする方法について説明します。
ms.openlocfilehash: d9a07eb333b0abdb3cb6a890ac2de3d19ad3685b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192645"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Microsoft 365でアプリに対するユーザーの同意を管理する

この設定は、ユーザーがサインインとデータへのアクセス要求に OpenID Connectと OAuth 2.0 を使用するアプリにその同意を与えることができるかどうかを制御します。 アプリは、自分の組織内から作成することも、別のOffice 365組織またはサード パーティから作成することもできます。

この設定をオンにすると、これらのアプリは組織のデータにアクセスするためのアクセス許可をユーザーに求め、ユーザーはそれを許可するかどうかを選択できます。 この設定をオフにした場合、ユーザーがアプリを使用する前に、管理者はそれらのアプリに同意する必要があります。 この場合は、ユーザーがブロックされたアプリを使用するための管理者承認要求を送信できるように、Azure portalで管理者の同意ワークフローを設定することを検討してください。

ユーザーは、Office 365 情報に対して自分自身が持っているアクセス権のみをアプリに与えることができます。 他のユーザーの情報に対して、アプリにアクセス権を与えることはできません。

## <a name="turning-user-consent-on-or-off"></a>ユーザーの同意のオンとオフを切り替える

アプリに対するユーザーの同意を有効または無効にする方法を次に示します。

1. 管理センターで、[**設定** \> **組織の設定** > [サービス](https://go.microsoft.com/fwlink/p/?linkid=2053743)] ページに移動し、[**アプリに対するユーザーの同意**] を選択します。

2. [ **アプリに対するユーザーの同意** ] ページで、ユーザーの同意をオンまたはオフにするオプションを選択します。

## <a name="related-content"></a>関連コンテンツ 

[管理者の同意ワークフローを構成する](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (記事)\
[アプリケーションへの同意の管理と同意要求の評価](/azure/active-directory/manage-apps/manage-consent-requests) (記事)