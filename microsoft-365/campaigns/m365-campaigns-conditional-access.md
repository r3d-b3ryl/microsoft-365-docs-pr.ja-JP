---
title: 条件付きアクセスポリシーを設定する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: MFA を要求する方法と、Microsoft 365 Business の条件付きアクセスポリシーを設定する方法について説明します。
ms.openlocfilehash: 7898ded24bb66545b903ab98f3c7aa78d95860f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42056419"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>多要素認証を必要とし、条件付きアクセスポリシーを設定する

多要素認証および条件付きアクセスポリシーを使用して、データへのアクセスを保護します。 これらにより、セキュリティが大幅に強化します。 Microsoft は、すべてのお客様に推奨される基準条件付きアクセスポリシーのセットを提供しています。 ベースラインポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ、定義済みのポリシーのセットです。 これらの一般的な攻撃には、パスワードのスプレー、リプレイ、フィッシングを含めることができます。

これらのポリシーでは、管理者とユーザーは、一定の条件が満たされたときに、2番目の形式の認証 (多要素認証または MFA と呼ばれる) を入力する必要があります。 たとえば、組織内のユーザーが、別の国または不明なデバイスから Microsoft 365 にサインインしようとした場合、そのサインインは危険であると見なされることがあります。 ユーザーは、id を証明するために、特別な形式の認証 (指紋やコードなど) を提供する必要があります。 

現在、ベースラインポリシーには次のものが含まれています。
- Microsoft 365 管理センターでのセットアップ:
    - 管理者**に MFA を要求**—グローバル管理者を含む、最も特権のある管理者の役割に対して多要素認証が必要です。
    - **エンドユーザーによる保護**—サインインが危険な場合にのみ、ユーザーに対して多要素認証が必要です。 
- Azure Active Directory ポータルで設定します。
    - **従来の認証をブロック**する: 以前のクライアントアプリや一部の新しいアプリでは、より新しい、より安全な認証プロトコルを使用しません。 これらの古いアプリは、条件付きアクセスポリシーをバイパスし、環境への権限のないアクセスを取得できます。 このポリシーは、条件付きアクセスをサポートしていないクライアントからのアクセスをブロックします。 
    - **サービス管理に MFA を必要と**する— Azure portal を含む、管理ツールへのアクセスに多要素認証が必要です (基準ポリシーの構成場所)。 

Microsoft では、これらのベースラインポリシーのすべてを有効にすることをお勧めします。 これらのポリシーが有効になると、管理者とユーザーは Azure 多要素認証を登録するように求められます。

これらのポリシーの詳細については、「 [baseline ポリシーとは](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)」を参照してください。


## <a name="require-mfa"></a>MFA を要求

すべてのユーザーに2番目の形式の ID を使用してサインインするよう要求するには、次のようにします。

1. 管理センターに移動し<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>て、[**セットアップ**] を選びます。

2. [セットアップ] ページで、[サインイン] の [**セキュリティで保護さ**れたカードの作成] で [**表示**] を選択します。


    ![サインインして、より安全なカードを作成します。](../media/setupmfa.png)
3. [サインインを強化する] ページで、[**開始**] を選択します。
 
4. [サインインのセキュリティを強化する] ウィンドウで、[**管理者に多要素認証を必要**とする] の横にあるチェックボックスをオンにし、[**ユーザーに多要素認証の登録を要求し、リスクが検出された場合はアクセスをブロック**する] チェックボックスをオンにします。
    [**ユーザーの検索**] ボックスの [MFA] 要件から、[緊急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)または "破損" 管理者アカウントを除外するようにしてください。
    
    ![[セキュリティを強化する] ページ。](../media/requiremfa.png)

5. ページの下部にある [**ポリシーの作成**] を選択します。

## <a name="set-up-baseline-policies"></a>ベースラインポリシーを設定する

1. [Azure portal](https://portal.azure.com)に移動して、 **azure Active Directory** \>の**条件付きアクセス**に移動します。
    
    ベースラインポリシーはページに一覧表示されており、管理者と**エンドユーザー保護****を必要**とする手順が完了した後、 [mfa が必要](#require-mfa)であることがわかります。

    ![条件付きアクセスのベースラインポリシーを一覧表示するページ。](../media/casettings.png)
2. 各ポリシーについて、次の具体的な手順を参照してください。

    - [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [ユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [サービス管理に MFA を必要とする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

承認済みのクライアントアプリの要求など、特別なポリシーを設定できます。 詳細については、[条件付きアクセスのドキュメント](https://docs.microsoft.com/azure/active-directory/conditional-access/)を参照してください。
