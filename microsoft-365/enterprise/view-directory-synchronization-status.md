---
title: Microsoft 365 でのディレクトリ同期状態の表示
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
description: この記事では、Office 365 でディレクトリ同期の状態を確認する方法について説明します。
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326951"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Microsoft 365 でのディレクトリ同期状態の表示

オンプレミス環境と Microsoft 365 を同期することによって、オンプレミスの Active Directory ドメインサービス (AD DS) と Azure Active Directory (Azure AD) が統合されている場合は、同期の状態を確認することもできます。
  
## <a name="view-directory-synchronization-status"></a>ディレクトリ同期の状態を表示する

- [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインし、ホームページの [ **DirSync Status** ] を選択します。
- または、[アクティブなユーザー] ページ**に移動**し、[ \> **Active users****アクティブなユーザー** ] ページで、[ディレクトリ同期の**追加**] を選択し \> **Directory synchronization**ます。 [ **ディレクトリ同期** ] ウィンドウで、[ **DirSync management に移動] を**選択します。

## <a name="information-on-the-manage-directory-synchronization-page"></a>[ディレクトリ同期の管理] ページの情報

次の表に、ページの情報を取得できる機能を示します。
  
ディレクトリ同期に問題がある場合は、このページにもエラーが表示されます。 発生する可能性のあるさまざまなエラーの詳細については、「 [Microsoft 365 でのディレクトリ同期エラーの識別](identify-directory-synchronization-errors.md)」を参照してください。
  
|アイテム|目的|
|:-----|:-----|
|**確認されたドメイン** | 自分が所有していることを確認した Microsoft 365 テナント内のドメインの数。 |
|**確認されていないドメイン** | 追加されたが確認されていないドメイン。 |
|**ディレクトリ同期の有効化** |True または False。 ディレクトリ同期を有効にしたかどうかを指定します。 |
|**最新のディレクトリ同期** | ディレクトリ同期が最後に実行した時刻。 前回の同期が3日以上前の場合は、警告とトラブルシューティングツールへのリンクが表示されます。 |
|**パスワード同期の有効化** | True または False。 オンプレミスと Microsoft 365 テナント間でパスワードハッシュを同期するかどうかを指定します。 |
|**前回のパスワード同期** | 前回のパスワードハッシュ同期を実行した時刻。 前回の同期が3日以上前の場合は、警告とトラブルシューティングツールへのリンクが表示されます。 |
|**ディレクトリ同期クライアントバージョン** | Azure AD Connect の新しいバージョンがリリースされた場合のダウンロードリンクが含まれています。 |
|**ディレクトリ同期サービスアカウント** | Microsoft 365 ディレクトリ同期サービスアカウントの名前を表示します。 |
|||

## <a name="monitor-synchronization-health"></a>同期の状態を監視する

このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。 監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。

Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。

- **管理認証**オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。
- Active Directory フェデレーション サービス (AD FS) で**フェデレーション認証**を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。

完了すると、次のことができます。

- Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。
- Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。

