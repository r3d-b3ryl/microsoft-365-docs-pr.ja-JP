---
title: '[ディレクトリ同期の状態を表示する] Microsoft 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: この記事では、ディレクトリ同期の状態を確認する方法について、Office 365。
ms.openlocfilehash: 766e3ef112ac9493863df0aa6c9958e89ec93c0e2e0c9e307e7371b536f3cb01
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53840757"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>[ディレクトリ同期の状態を表示する] Microsoft 365

オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure Active Directory (Azure AD) と統合した場合は、オンプレミス環境と Microsoft 365 を同期することで、同期の状態を確認できます。
  
## <a name="view-directory-synchronization-status"></a>ディレクトリ同期の状態を表示する

- ホーム ページに [サインインMicrosoft 365 管理センター](https://admin.microsoft.com)し、ホーム ページ **で [DirSync Status]** を選択します。
- または、[ユーザー] [アクティブな **ユーザー]** に移動し、[アクティブなユーザー] ページで [その他のディレクトリ \> 同期] \> **を選択します**。 [ディレクトリ同期 **] ウィンドウで****、[DirSync 管理に移動] を選択します**。

## <a name="information-on-the-manage-directory-synchronization-page"></a>[ディレクトリ同期の管理] ページの情報

次の表に、ページで情報を取得できる機能の一覧を示します。
  
ディレクトリ同期に問題がある場合は、このページにもエラーが表示されます。 発生する可能性のあるさまざまなエラーの詳細については、「ディレクトリ同期エラーを特定する」を参照[Microsoft 365。](identify-directory-synchronization-errors.md)
  
|アイテム|目的|
|:-----|:-----|
|**ドメインが検証済み** | ユーザーが所有しているMicrosoft 365しているドメインの数。 |
|**ドメインが検証されていない** | 追加したが、検証されていないドメイン。 |
|**ディレクトリ同期が有効** |True または False。 ディレクトリ同期を有効にしたかどうかを指定します。 |
|**最新のディレクトリ同期** | ディレクトリ同期が実行された最後の時間。 前回の同期が 3 日以上前の場合は、警告とトラブルシューティング ツールへのリンクが表示されます。 |
|**パスワード同期が有効** | True または False。 オンプレミステナントとテナント間でパスワード ハッシュ同期を行うかどうかをMicrosoft 365します。 |
|**最後のパスワード同期** | 前回のパスワード ハッシュ同期が実行された時間。 前回の同期が 3 日以上前の場合は、警告とトラブルシューティング ツールへのリンクが表示されます。 |
|**ディレクトリ同期クライアントのバージョン** | 新しいバージョンの Azure アプリケーションがリリースされている場合はAD Connectリンクが含まれる。 |
|**ディレクトリ同期サービス アカウント** | ディレクトリ同期サービス アカウントMicrosoft 365を表示します。 |
|||

## <a name="monitor-synchronization-health"></a>同期の状態を監視する

このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。 監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。

Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。

- **管理認証** オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。
- Active Directory フェデレーション サービス (AD FS) で **フェデレーション認証** を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。

完了すると、次の情報が表示されます。

- Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。
- Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。