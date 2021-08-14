---
title: セルフサービス サインアップ サブスクリプションの管理
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: 組織の無料セルフサービス サインアップ サブスクリプションを管理する方法について学習します。
ms.date: 03/17/2021
ms.openlocfilehash: b942d21fb3c4a6d6b8ab27fafb2af00a095c2a608909142788e46dbe60cdfa9d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53852153"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>セルフサービス サインアップ サブスクリプションの管理

## <a name="what-are-self-service-sign-up-subscriptions"></a>セルフサービス サインアップ サブスクリプションとは

組織内のユーザーがサインアップできる無料のセルフサービス サインアップ サブスクリプションの数は限られています。 ユーザーがサインアップできるのは、自己サービスサインアップ サブスクリプションのみです。 セルフサービス サインアップ サブスクリプションを管理するには、ユーザーのサインアップをブロックし、ユーザーがサインアップした無料のサブスクリプションを削除します。 セルフサービス サインアップと利用可能なサブスクリプションの詳細については、「組織でのセルフサービス サインアップの使用 [」を参照してください](../../admin/misc/self-service-sign-up.md)。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>セルフサービス サインアップ サブスクリプションの一覧を表示する

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブで** 、フィルター アイコンを選択し、[無料] を **選択します**。 すべてのセルフサービス サインアップ サブスクリプションの一覧が表示されます。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>これらのサブスクリプションとセルフサービス購入サブスクリプションの違いは何ですか?

セルフサービス サインアップ サブスクリプションは無料で、セルフサービス購入サブスクリプションよりも大きな製品リストで利用できます。 ユーザーがセルフサービス購入サブスクリプションに登録すると、ユーザーは支払いを行う責任があります。 セルフサービス購入サブスクリプションは、Power Platform 製品 (Power BI、Power Apps、および Power Automate)、Project、および Visio でのみ利用できます。 詳細については、「セルフサービス購入 [に関するよく寄せられる質問」を参照してください](self-service-purchase-faq.yml)。

## <a name="block-users-from-signing-up"></a>ユーザーのサインアップをブロックする

ユーザーがセルフサービス サインアップ サブスクリプションにサインアップできるかどうかを制御するには **、AllowAdHocSubscriptions** パラメーターを使用して [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0)コマンドレットを使用します。 詳細については、「セルフサービス設定 [を制御する方法」を参照してください。](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>セルフサービス サインアップ サブスクリプションを削除する

> [!IMPORTANT]
> セルフサービス サインアップ サブスクリプションを削除すると、すべてのユーザーが自分のデータと電子メールにアクセスし、すべてのデータと電子メールを削除できます。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. [製品 **] タブで** 、フィルター アイコンを選択し、[無料] を **選択します**。
3. 削除するセルフサービス サインアップ サブスクリプションを選択します。 
4. [サブスクリプションの詳細] ページの [ **サブスクリプションと支払** いの設定] セクションで、[サブスクリプションの削除] **を選択します**。
5. [サブスクリプション **の削除] ウィンドウで** 、チェック ボックスをオンにして、[サブスクリプションの削除] **を選択します**。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>ディレクトリの削除をブロックするセルフサービス サインアップ サブスクリプションがある

個々のユーザーがサインアップできるセルフサービスサインアップ製品は、Azure AD ディレクトリに認証用のゲスト ユーザーを作成します。 データの損失を回避するために、これらのセルフサービス製品は、ディレクトリから完全に削除されるまで、ディレクトリの削除をブロックします。 削除できるのは、Azure 管理者ADのみです。詳細については、「ディレクトリを削除[する」を参照Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-delete-howto)
