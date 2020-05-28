---
title: セルフサービスのサインアップサブスクリプションを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 組織の無料セルフサービスサインアップサブスクリプションを管理する方法について説明します。
ms.openlocfilehash: 81c67292a394c62d6057022babb88aa8796b9b3d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403248"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>セルフサービスのサインアップサブスクリプションを管理する

## <a name="what-are-self-service-sign-up-subscriptions"></a>セルフサービスのサインアップサブスクリプションとは

組織内のユーザーがサインアップできる無料のセルフサービスサインアップサブスクリプションの数には制限があります。 ユーザーは自分でサインアップし、セルフサービスのサインアップサブスクリプションを自分自身に対してのみ使用できます。 これらのサブスクリプションは、[**製品**] ページに表示され、**空き**のマークが付けられ、"社内のユーザーによってライセンス認証が完了しました" というメモがあります。 セルフサービスのサインアップサブスクリプションを管理するには、ユーザーのサインアップをブロックし、ユーザーがサインアップした無料のサブスクリプションを削除します。 セルフサービスのサインアップと利用可能なサブスクリプションの詳細については、「[組織でのセルフサービスサインアップの使用](../../admin/misc/self-service-sign-up.md)」を参照してください。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>これらのサブスクリプションはセルフサービス購入サブスクリプションとどのような違いがありますか?

セルフサービスサインアップサブスクリプションは無料であり、セルフサービス購入サブスクリプションよりも多くの製品リストで利用できます。 ユーザーがセルフサービス購入サブスクリプションにサインアップすると、ユーザーはそれに対して支払いを担当します。 また、セルフサービス購入サブスクリプションは、電源プラットフォーム製品 (Power BI、電源アプリ、および電源の自動化) に対してのみ使用できます。 詳細については、「[セルフサービス購入](self-service-purchase-faq.md)に関する FAQ」を参照してください。

## <a name="block-users-from-signing-up"></a>ユーザーのサインアップをブロックする

[**Set-msolcompanysettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)コマンドレットを**AllowAdHocSubscriptions**パラメーターと共に使用して、ユーザーがセルフサービスサインアップサブスクリプションにサインアップできるかどうかを制御します。 詳細については、「[セルフサービス設定を制御する方法](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)」を参照してください。

## <a name="delete-a-self-service-sign-up-subscription"></a>セルフサービスのサインアップサブスクリプションを削除する

> [!IMPORTANT]
> セルフサービスのサインアップサブスクリプションを削除すると、すべてのユーザーが自分のデータや電子メールにアクセスしたり、すべてのデータとメールを削除したりするのをブロックします。

1. 管理センターで、**[課金]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">[製品]</a> ページの順に移動します。
2. 削除するセルフサービスのサインアップサブスクリプションを検索します。 [**設定 &** の [アクション] セクションで、[**サブスクリプションの削除**] を選択します。
3. [**サブスクリプションの削除**] ウィンドウで、チェックボックスをオンにして、[**サブスクリプションの削除**] を選択します。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>ディレクトリの削除をブロックするセルフサービスのサインアップサブスクリプションがあります

個々のユーザーがサインアップできるセルフサービスサインアップ製品は、Azure AD ディレクトリで認証のためのゲストユーザーを作成することもできます。 データ損失を回避するため、これらのセルフサービス製品はディレクトリから完全に削除されるまでディレクトリの削除をブロックします。 Azure AD 管理者のみが削除できます。詳細については、「 [Azure Active directory でディレクトリを削除する](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)」を参照してください。