---
title: ユーザーのディレクトリ同期をMicrosoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
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
description: ユーザーとオンプレミスの Active Directory の間Microsoft 365同期を設定する方法について学習します。
ms.openlocfilehash: db6fc46eb4659b0c41f46b2828044af3bdaf02e2
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356194"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>ユーザーのディレクトリ同期をMicrosoft 365

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365は、Azure Active Directory (Azure AD) テナントを使用して、クラウドベースのリソースにアクセスするための認証とアクセス許可の ID を格納および管理します。 

オンプレミスの Active Directory ドメイン サービス (AD DS) ドメインまたはフォレストがある場合は、AD DS ユーザー アカウント、グループ、および連絡先を Microsoft 365 サブスクリプションの Azure AD テナントと同期できます。 これは、ユーザーのハイブリッド id Microsoft 365。 そのコンポーネントを次に示します。

![ディレクトリ同期のコンポーネント (Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connectオンプレミス サーバー上で実行され、DS と Azure ADテナントをADします。 ディレクトリ同期と共に、次の認証オプションを指定できます。

- パスワード ハッシュ同期 (PHS)

  Azure AD認証自体を実行します。

- パススルー認証 (PTA)

  Azure AD DS AD認証を実行しています。

- フェデレーション認証

  Azure ADは、認証を要求するクライアント コンピューターを別の ID プロバイダーに参照します。

詳細 [については、「ハイブリッド ID」](plan-for-directory-synchronization.md) を参照してください。
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Azure の前提条件を確認AD Connect

サブスクリプションで無料の Azure ADサブスクリプションをMicrosoft 365します。 ディレクトリ同期を設定すると、Azure AD Connectオンプレミス サーバーの 1 つにインストールされます。
  
このMicrosoft 365、次の必要があります。
  
- オンプレミス ドメインを確認します。 Azure AD Connectウィザードでは、この手順を説明します。
- テナントおよび DS の管理者アカウントのユーザー名とパスワードMicrosoft 365取得ADします。

Azure AD Connectをインストールするオンプレミス サーバーの場合は、次の情報が必要です。
  
|**サーバー OS**|**その他のソフトウェア**|
|:-----|:-----|
|Windows Server 2012R2 以降 | - PowerShell は既定でインストールされ、アクションは必要ありません。  <br> - Net 4.5.1 以降のリリースは、更新プログラムを通じてWindowsされます。 コントロール パネルにサーバーに最新の更新Windowsインストールされていることを確認します。 |
|WindowsService Pack 1 (SP1)** またはサーバー 2008 R2 Windows Server 2012 | - PowerShell の最新バージョンは、Windows Management Framework 4.0 で使用できます。 Microsoft ダウンロード センターで [検索します](https://go.microsoft.com/fwlink/p/?LinkId=717996)。  <br> - .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センターで利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。 |
|Windows Server 2008 | - サポートされている最新バージョンの PowerShell は、Microsoft ダウンロード センター Windows Management Framework 3.0 から[利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。  <br> - .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センターで利用できます](https://go.microsoft.com/fwlink/p/?LinkId=717996)。 |

Azure [Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)のハードウェア、ソフトウェア、アカウント、およびアクセス許可の要件、SSL 証明書の要件、およびオブジェクトの制限の詳細については、「前提条件」を参照AD Connect。
  
また、Azure AD Connect[バージョン](/azure/active-directory/hybrid/reference-connect-version-history)のリリース履歴を確認して、各リリースに含まれているものと修正された情報を確認できます。

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD Connectをインストールし、ディレクトリ同期を構成する

開始する前に、次の情報が必要です。

- グローバル管理者のユーザー名Microsoft 365パスワード
- DS ドメイン管理者のユーザー ADパスワード
- どの認証方法 (PHS、PTA、フェデレーション)
- シームレス シングル サインオン [(SSO) で Azure ADを使用するかどうか](/azure/active-directory/hybrid/how-to-connect-sso)

次の手順を実行します。

1. [ユーザー] ウィンドウに [サインインMicrosoft 365 管理センター](https://admin.microsoft.com)し https://admin.microsoft.com) 、左側のナビゲーションで [**ユーザー** \> **のアクティブユーザー** ] を選択します。
2. [アクティブ ユーザー **] ページで** 、[その他 ( **3** つのドット) ディレクトリ同期] \> **を選択します**。
  
3. [準備 **Azure Active Directoryページで**、[ダウンロード センターに移動] を選択して **、[Azure AD Connectツール**] リンクを取得して開始します。 
4. Azure AD Connect[および Azure AD Connect 正常性インストール のロードマップの手順に従います](/azure/active-directory/hybrid/how-to-connect-install-roadmap)。

## <a name="3-finish-setting-up-domains"></a>3. ドメインの設定を完了する

DNS レコードを管理してドメインのセットアップをMicrosoft 365するときに、「ドメインの DNS レコード[を](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)作成する」の手順に従います。

## <a name="next-step"></a>次の手順

[ユーザー アカウントにライセンスを割り当てる](assign-licenses-to-user-accounts.md)