---
title: セルフサービス サインアップ サブスクリプションを管理する
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
search.appverid: MET150
description: 組織の無料のセルフサービス サインアップ サブスクリプションを管理する方法について説明します。
ms.date: 03/17/2021
ms.openlocfilehash: 58c58c849b72c170e0ccf10de54389bd1245bced
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102352"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>セルフサービス サインアップ サブスクリプションを管理する

## <a name="what-are-self-service-sign-up-subscriptions"></a>セルフサービス サインアップ サブスクリプションとは何ですか?

組織内のユーザーがサインアップできる無料のセルフサービス サインアップ サブスクリプションの数には制限があります。 ユーザーがサインアップして使用できるのは、セルフサービス サインアップ サブスクリプションのみです。 セルフサービス サインアップ サブスクリプションを管理するには、ユーザーのサインアップをブロックし、ユーザーがサインアップした無料サブスクリプションを削除します。 セルフサービス サインアップと使用可能なサブスクリプションの詳細については、「 [組織でのセルフサービス サインアップの使用](../../admin/misc/self-service-sign-up.md)」を参照してください。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>セルフサービス サインアップ サブスクリプションの一覧を表示する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [ **製品** ] タブでフィルター アイコンを選択し、[ **無料**] を選択します。 すべてのセルフサービス サインアップ サブスクリプションの一覧が表示されます。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>これらのサブスクリプションとセルフサービス購入サブスクリプションの違いは何ですか?

セルフサービス サインアップ サブスクリプションは無料で、セルフサービス購入サブスクリプションよりも多くの製品の一覧で利用できます。 ユーザーがセルフサービス購入サブスクリプションにサインアップすると、そのサブスクリプションに対する支払いを担当します。 セルフサービス購入サブスクリプションは、Power Platform 製品 (Power BI、Power Apps、Power Automate)、Project、Visioでのみ使用できます。 詳細については、「 [セルフサービス購入に関する FAQ](self-service-purchase-faq.yml)」を参照してください。

## <a name="block-users-from-signing-up"></a>ユーザーのサインアップをブロックする

[**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) コマンドレットと **AllowAdHocSubscriptions** パラメーターを使用して、ユーザーがセルフサービス サインアップ サブスクリプションにサインアップできるかどうかを制御します。 詳細については、「[セルフサービス設定操作方法制御](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)する」を参照してください。

## <a name="delete-a-self-service-sign-up-subscription"></a>セルフサービス サインアップ サブスクリプションを削除する

> [!IMPORTANT]
> セルフサービス サインアップ サブスクリプションを削除すると、すべてのユーザーが自分のデータと電子メールにアクセスできないようにブロックし、すべてのデータと電子メールを削除します。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [ **製品** ] タブでフィルター アイコンを選択し、[ **無料**] を選択します。
3. 削除するセルフサービス サインアップ サブスクリプションを選択します。 
4. [サブスクリプションの詳細] ページの [ **サブスクリプションと支払いの設定** ] セクションで、[ **サブスクリプションの削除**] を選択します。
5. [ **サブスクリプションの削除** ] ウィンドウで、チェック ボックスをオンにし、[ **サブスクリプションの削除**] を選択します。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>ディレクトリの削除をブロックするセルフサービス サインアップ サブスクリプションがある

個々のユーザーがサインアップできるセルフサービス サインアップ製品も、Azure AD ディレクトリに認証用のゲスト ユーザーを作成します。 データ損失を回避するために、これらのセルフサービス製品は、ディレクトリから完全に削除されるまでディレクトリの削除をブロックします。 削除できるのは、Azure AD 管理者のみです。詳細については、「[Azure Active Directoryのディレクトリを削除する](/azure/active-directory/users-groups-roles/directory-delete-howto)」を参照してください。
