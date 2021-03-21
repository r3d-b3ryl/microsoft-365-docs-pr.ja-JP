---
title: Microsoft 365 のディレクトリ同期を設定する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Microsoft 365 とオンプレミスの Active Directory の間でディレクトリ同期を設定する方法について説明します。
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924906"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Microsoft 365 のディレクトリ同期を設定する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 では、Azure Active Directory (Azure AD) テナントを使用して、クラウドベースのリソースにアクセスするための認証とアクセス許可の ID を格納および管理します。 

オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインまたはフォレストがある場合は、microsoft 365 サブスクリプションの Azure AD テナントと AD DS ユーザー アカウント、グループ、連絡先を同期できます。 これは、Microsoft 365 のハイブリッド ID です。 そのコンポーネントを次に示します。

![Microsoft 365 のディレクトリ同期のコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect はオンプレミス サーバー上で実行され、DS と Azure ADテナントをADします。 ディレクトリ同期と共に、次の認証オプションを指定できます。

- パスワード ハッシュ同期 (PHS)

  Azure AD認証自体を実行します。

- パススルー認証 (PTA)

  Azure AD DS AD認証を実行しています。

- フェデレーション認証

  Azure ADは、認証を要求するクライアント コンピューターを別の ID プロバイダーに参照します。

詳細 [については、「ハイブリッド ID」](plan-for-directory-synchronization.md) を参照してください。
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Azure AD Connect の前提条件を確認する

Microsoft 365 サブスクリプションで無料の Azure ADサブスクリプションを取得します。 ディレクトリ同期を設定すると、Azure AD接続をオンプレミス サーバーの 1 つにインストールします。
  
Microsoft 365 の場合は、次の必要があります。
  
- オンプレミス ドメインを確認します。 Azure AD接続ウィザードでは、この手順について説明します。
- Microsoft 365 テナントの管理者アカウントのユーザー名とパスワードを取得し、DS ADします。

Azure AD Connect をインストールするオンプレミス サーバーの場合は、次の情報が必要です。
  
|**サーバー OS**|**その他のソフトウェア**|
|:-----|:-----|
|Windows Server 2012 R2 以降 | - PowerShell は既定でインストールされ、アクションは必要ありません。  <br> - Net 4.5.1 以降のリリースは、Windows Update を通じて提供されます。 コントロール パネルに Windows Server の最新の更新プログラムがインストールされていることを確認します。 |
|Windows Server 2008 R2パック 1 (SP1)** またはサービス Windows Server 2012 | - PowerShell の最新バージョンは、Windows Management Framework 4.0 で使用できます。 Microsoft ダウンロード センターで [検索します](https://go.microsoft.com/fwlink/p/?LinkId=717996)。  <br> - .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センターで利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。 |
|Windows Server 2008 | - サポートされている最新バージョンの PowerShell は、Microsoft ダウンロード センター Windows Management Framework 3.0 から [利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。  <br> - .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センターで利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。 |

Azure AD Connect のハードウェア、ソフトウェア、アカウントとアクセス許可の要件、SSL 証明書の要件、およびオブジェクト制限の詳細については [、「Azure Active Directory](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) Connect の前提条件」を参照してください。
  
Azure AD [Connect](/azure/active-directory/hybrid/reference-connect-version-history) のバージョン リリース履歴を確認して、各リリースに含まれているものと修正された情報を確認できます。

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure ADをインストールし、ディレクトリ同期を構成する

開始する前に、次の情報が必要です。

- Microsoft 365 グローバル管理者のユーザー名とパスワード
- DS ドメイン管理者のユーザー ADパスワード
- どの認証方法 (PHS、PTA、フェデレーション)
- シームレス シングル サインオン [(SSO) で Azure ADを使用するかどうか](/azure/active-directory/hybrid/how-to-connect-sso)

次の手順を実行します。

1. [Microsoft 365](https://admin.microsoft.com)管理センターにサインインし、 https://admin.microsoft.com) 左側のナビゲーションで [**ユーザー** \> **のアクティブ** ユーザー] を選択します。
2. [アクティブ ユーザー **] ページで** 、[その他 ( **3** つのドット) ディレクトリ同期] \> **を選択します**。
  
3. **[Azure Active Directory の** 準備] ページで、[ダウンロード センターに移動] を選択して **、[Azure** AD接続] ツールリンクを取得して開始します。 
4. Azure AD [接続と Azure ADインストール ロードマップの手順に従います](/azure/active-directory/hybrid/how-to-connect-install-roadmap)。

## <a name="3-finish-setting-up-domains"></a>3. ドメインの設定を完了する

DNS レコードを管理してドメインのセットアップを完了する [場合は、「Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) の DNS レコードを作成する」の手順に従います。

## <a name="next-step"></a>次の手順

[ユーザー アカウントにライセンスを割り当てる](assign-licenses-to-user-accounts.md)