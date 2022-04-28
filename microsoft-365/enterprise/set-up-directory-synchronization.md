---
title: Microsoft 365のディレクトリ同期を設定する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Microsoft 365とオンプレミスの Active Directoryの間でディレクトリ同期を設定する方法について説明します。
ms.openlocfilehash: 49240d056520a83c0828440e21c5cf26943bae8e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092891"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Microsoft 365のディレクトリ同期を設定する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365では、Azure Active Directory (Azure AD) テナントを使用して、認証とアクセス許可の ID を格納および管理してクラウドベースのリソースにアクセスします。 

オンプレミスの Active Directory Domain Services (AD DS) ドメインまたはフォレストがある場合は、AD DS のユーザー アカウント、グループ、連絡先をMicrosoft 365 サブスクリプションのAzure AD テナントと同期できます。 これは、Microsoft 365のハイブリッド ID です。 そのコンポーネントを次に示します。

![Microsoft 365のディレクトリ同期のコンポーネント。](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connectはオンプレミス サーバーで実行され、AD DS をAzure AD テナントと同期します。 ディレクトリ同期と共に、次の認証オプションを指定することもできます。

- パスワード ハッシュ同期 (PHS)

  Azure ADは認証自体を実行します。

- パススルー認証 (PTA)

  AD DS に認証を実行Azure AD。

- フェデレーション認証

  Azure ADは、認証を要求しているクライアント コンピューターを別の ID プロバイダーに参照します。

詳細については、「 [ハイブリッド ID」](plan-for-directory-synchronization.md) を参照してください。
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Azure AD Connectの前提条件を確認する

Microsoft 365 サブスクリプションで無料のAzure AD サブスクリプションを取得します。 ディレクトリ同期を設定すると、オンプレミスサーバーのいずれかにAzure AD Connectをインストールします。
  
Microsoft 365の場合は、次の手順を実行する必要があります。
  
- オンプレミス ドメインを確認します。 Azure AD Connect ウィザードでは、この操作をガイドします。
- Microsoft 365 テナントと AD DS の管理者アカウントのユーザー名とパスワードを取得します。

Azure AD Connectをインストールするオンプレミス サーバーの場合は、次のものが必要です。
  
|**サーバー OS**|**その他のソフトウェア**|
|:-----|:-----|
|Windows Server 2012 R2 以降 | - PowerShell は既定でインストールされ、アクションは必要ありません。  <br> - Net 4.5.1 以降のリリースは、Windows Updateを通じて提供されます。 コントロール パネルで、Windows Server に対する最新の更新プログラムがインストールされていることを確認します。 |
|Windows Server 2008 R2 と Service Pack 1 (SP1)** またはWindows Server 2012 | - PowerShell の最新バージョンは、Windows Management Framework 4.0 で使用できます。 [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/p/?LinkId=717996)で検索します。  <br> - .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/p/?LinkId=717996)で入手できます。 |
|Windows Server 2008 | - サポートされている最新バージョンの PowerShell は、[Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/p/?LinkId=717996)で入手できる Windows Management Framework 3.0 で入手できます。  <br> - .Net 4.5.1 以降のリリースは [、Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/p/?LinkId=717996)で入手できます。 |

ハードウェア、ソフトウェア、アカウントとアクセス許可の要件、SSL 証明書の要件、およびAzure AD Connectのオブジェクトの制限の詳細については、「Azure Active Directory Connectの[前提条件」](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)を参照してください。
  
Azure AD Connect[バージョンのリリース履歴](/azure/active-directory/hybrid/reference-connect-version-history)を確認して、各リリースに含まれる内容と修正内容を確認することもできます。

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD Connectをインストールし、ディレクトリ同期を構成する

開始する前に、次の情報があることを確認します。

- Microsoft 365グローバル管理者のユーザー名とパスワード
- AD DS ドメイン管理者のユーザー名とパスワード
- どの認証方法 (PHS、PTA、フェデレーション)
- [シームレス シングル サインオン (SSO) Azure AD](/azure/active-directory/hybrid/how-to-connect-sso)使用するかどうか

次の手順を実行します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインし、https://admin.microsoft.com)左側のナビゲーションで [**ユーザー** \> **アクティブ ユーザー**] を選択します。
2. **[アクティブ ユーザー**] ページで、[**その他** の (3 つのドット) **ディレクトリ同期**] \> を選択します。
  
3. **Azure Active Directory準備** ページで、[**ダウンロード センターに移動] を選択して、Azure AD Connect ツール** のリンクを取得します。 
4. [Azure AD ConnectとAzure AD Connect正常性のインストール ロードマップ](/azure/active-directory/hybrid/how-to-connect-install-roadmap)の手順に従います。

## <a name="3-finish-setting-up-domains"></a>3. ドメインの設定を完了する

ドメインの設定を完了するために [DNS レコードを管理する場合は、「Microsoft 365の DNS レコードを作成](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)する」の手順に従います。

## <a name="next-step"></a>次の手順

[ユーザー アカウントにライセンスを割り当てる](assign-licenses-to-user-accounts.md)