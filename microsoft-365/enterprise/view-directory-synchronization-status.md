---
title: Microsoft 365でディレクトリ同期の状態を表示する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: この記事では、Office 365でディレクトリ同期の状態を確認する方法について説明します。
ms.openlocfilehash: 8f21985f8db3539e8dd1a839cc6cb499a425feeb
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095556"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Microsoft 365でディレクトリ同期の状態を表示する

オンプレミス環境とMicrosoft 365を同期することで、オンプレミスの Active Directory Domain Services (AD DS) と Azure Active Directory (Azure AD) を統合している場合は、同期の状態を確認することもできます。
  
## <a name="view-directory-synchronization-status"></a>ディレクトリ同期の状態を表示する

- [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインし、ホーム ページで **[DirSync 状態]** を選択します。
- または、[ユーザー **のアクティブユーザー****]** \> に移動し、[**アクティブなユーザー**] ページで [**その他**\>の **ディレクトリ同期**] を選択することもできます。 [ **ディレクトリ同期** ] ウィンドウで、[ **DirSync 管理に移動**] を選択します。

## <a name="information-on-the-manage-directory-synchronization-page"></a>[ディレクトリ同期の管理] ページの情報

次の表に、ページに関する情報を取得できる機能の一覧を示します。
  
ディレクトリ同期に問題がある場合は、このページにもエラーが一覧表示されます。 発生する可能性があるさまざまなエラーの詳細については、「[Microsoft 365でディレクトリ同期エラーを識別する](identify-directory-synchronization-errors.md)」を参照してください。
  
|アイテム|目的|
|:-----|:-----|
|**検証されたドメイン** | 所有していることを確認したMicrosoft 365 テナント内のドメインの数。 |
|**検証されていないドメイン** | 追加したが検証されていないドメイン。 |
|**ディレクトリ同期が有効になっている** |True または False。 ディレクトリ同期を有効にするかどうかを指定します。 |
|**最新のディレクトリ同期** | 前回ディレクトリ同期が実行されました。 最後の同期が 3 日前を超えた場合は、警告とトラブルシューティング ツールへのリンクが表示されます。 |
|**パスワード同期が有効になっている** | True または False。 オンプレミスとMicrosoft 365 テナントの間でパスワード ハッシュ同期を行うかどうかを指定します。 |
|**最後のパスワード同期** | 前回パスワード ハッシュ同期が実行されました。 最後の同期が 3 日前を超えた場合は、警告とトラブルシューティング ツールへのリンクが表示されます。 |
|**ディレクトリ同期クライアントのバージョン** | 新しいバージョンのAzure AD Connectがリリースされた場合のダウンロード リンクが含まれます。 |
|**ディレクトリ同期サービス アカウント** | Microsoft 365 ディレクトリ同期サービス アカウントの名前を表示します。 |
|||

## <a name="monitor-synchronization-health"></a>同期の状態を監視する

このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。 監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。

Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。

- **管理認証** オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。
- Active Directory フェデレーション サービス (AD FS) で **フェデレーション認証** を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。

完了すると、次の情報が表示されます。

- Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。
- Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。