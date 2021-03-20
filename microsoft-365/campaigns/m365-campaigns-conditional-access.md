---
title: 条件付きアクセス ポリシーのセットアップ
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: MFA を要求し、ビジネス向け Microsoft 365 の条件付きアクセス ポリシーを設定する方法について説明します。
ms.openlocfilehash: dcb79ed060dd15fd288cdcfb9e3739a788f5fbc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912188"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>多要素認証を要求し、条件付きアクセス ポリシーを設定する

多要素認証と条件付きアクセス ポリシーを使用して、データへのアクセスを保護します。 これらは、大幅な追加のセキュリティを追加します。 Microsoft は、すべてのお客様に推奨される一連のベースライン条件付きアクセス ポリシーを提供します。 ベースライン ポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ一連の定義済みポリシーです。 これらの一般的な攻撃には、パスワード スプレー、再生、フィッシングが含まれます。

これらのポリシーでは、管理者とユーザーが特定の条件下で 2 つ目の認証形式 (多要素認証または MFA と呼ばれる) を入力する必要があります。 たとえば、組織内のユーザーが別の国または不明なデバイスから Microsoft 365 にサインインしようとすると、サインインは危険と見なされる可能性があります。 ユーザーは、自分の ID を証明するために、追加の形式の認証 (指紋やコードなど) を提供する必要があります。

現在、ベースライン ポリシーには次のポリシーが含まれます。

- Microsoft 365 管理センターでセットアップします。
  - **管理者に MFA を要求する**: グローバル管理者を含む、最も特権のある管理者の役割に対して多要素認証が必要です。
  - **エンド ユーザー保護**: サインインが危険な場合にのみ、ユーザーに多要素認証が必要です。 
- Azure Active Directory ポータルでのセットアップ:
  - **従来の認証をブロック** する: 古いクライアント アプリと一部の新しいアプリでは、より新しい、より安全な認証プロトコルを使用しない。 これらの古いアプリは、条件付きアクセス ポリシーをバイパスし、環境への未承認のアクセスを得る可能性があります。 このポリシーは、条件付きアクセスをサポートしないクライアントからのアクセスをブロックします。 
  - **サービス管理に MFA を** 要求する : Azure portal (ベースライン ポリシーを構成する場所) を含む管理ツールへのアクセスに多要素認証が必要です。

これらのベースライン ポリシーはすべて有効にすることをお勧めします。 これらのポリシーが有効になると、管理者とユーザーは、Azure 認証および多要素認証への登録を求ADされます。

これらのポリシーの詳細については、「ベースライン [ポリシーとは」を参照してください](/azure/active-directory/conditional-access/concept-baseline-protection)。

## <a name="require-mfa"></a>MFA を要求

すべてのユーザーが 2 番目の形式の ID でサインインする必要がある場合は、次の操作を行います。

1. 管理センターに移動し、[セットアップ <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ] を **選択します**。

2. [セットアップ] ページで、[ **サインインの** セキュリティを高くする] カードで **[表示] を選択** します。

    ![サインインのセキュリティを高くするカードを作成します。](../media/setupmfa.png)
3. [サインインのセキュリティを高める] ページで、[開始する] **を選択します**。

4. [サインイン セキュリティの強化] ウィンドウで、[管理者に多要素認証を要求する] と [ユーザーに多要素認証の登録を要求し、リスクが検出された場合はアクセスをブロックする] の横にあるチェック ボックスを **オンにします**。
    [ユーザーの検索] ボックス [の](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) MFA 要件から緊急または "ブレークガラス" 管理者アカウントを **除外してください** 。

    ![Sing-in セキュリティ ページを強化します。](../media/requiremfa.png)

5. ページ **の下部にある** [ポリシーの作成] を選択します。

## <a name="set-up-baseline-policies"></a>ベースライン ポリシーの設定

1. Azure portal に [移動し、[Azure](https://portal.azure.com) **Active Directory セキュリティ** 条件付きアクセス] に移動して \>  \> 新しいポリシー **を作成します**。

各ポリシーについては、次の具体的な手順を参照してください。 <br>
    - [管理者に MFA を要求する](/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [ユーザーに MFA を要求する](/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [従来の認証をブロックする](/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [サービス管理に MFA を要求する](/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> プレビュー ポリシーは存在しなくなったので、ユーザーは独自のポリシーを作成する必要があります。

承認されたクライアント アプリの要求など、追加のポリシーを設定できます。 詳細については、「条件付きアクセス」 [のドキュメントを参照してください](/azure/active-directory/conditional-access/)。