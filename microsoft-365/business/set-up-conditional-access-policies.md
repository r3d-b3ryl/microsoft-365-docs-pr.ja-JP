---
title: 条件付きアクセスポリシーを設定する
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business の条件付きアクセスポリシーをセットアップする方法について説明します。
ms.openlocfilehash: 6ca3995113f090ccf2b119abde059a68ce562970
ms.sourcegitcommit: ab04fea2765a63489d70b506f0e14303a5be16a0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "34806826"
---
# <a name="set-up-conditional-access-policies-for-microsoft-365-business"></a>Microsoft 365 Business の条件付きアクセスポリシーを設定する

[条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)ポリシー substancial 追加のセキュリティを追加します。 Microsoft は、すべてのお客様に推奨される基準条件付きアクセスポリシーのセットを提供しています。 ベースラインポリシーは、多くの一般的な攻撃から組織を保護するのに役立つ、定義済みのポリシーのセットです。 これらの一般的な攻撃には、パスワードのスプレー、リプレイ、フィッシングを含めることができます。

これらのポリシーでは、管理者とユーザーは、一定の条件が満たされたときに2番目の形式の認証 (多元的な認証、または MFA) を入力する必要があります。 たとえば、ユーザーが別の国からサインインしている場合、サインインが危険であると見なされ、ユーザーは追加の認証形式を提供する必要があります。 

現在、ベースラインポリシーには次のものが含まれています。
- 管理者**に MFA を要求**—グローバル管理者を含む、最も特権のある管理者の役割に対して多要素認証が必要です。
- **エンドユーザーによる保護**—サインインが危険な場合にのみ、ユーザーに対して多要素認証が必要です。 
- **従来の認証をブロック**する: 以前のクライアントアプリや一部の新しいアプリでは、より新しい、より安全な認証プロトコルを使用しません。 これらの古いアプリは、条件付きアクセスポリシーをバイパスし、環境への権限のないアクセスを取得できます。 このポリシーは、条件付きアクセスをサポートしていないクライアントからのアクセスをブロックします。 
- **サービス管理に MFA を必要と**する— Azure portal を含む、管理ツールへのアクセスに多要素認証が必要です (基準ポリシーの構成場所)。 

Microsoft では、これらのベースラインポリシーのすべてを有効にすることをお勧めします。 これらのポリシーを有効にした後、管理者とユーザーは Azure Multii authentication を登録するように求められます。

これらのポリシーの詳細については、「 [baseline ポリシーとは](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)」を参照してください。


## <a name="set-up-baseline-policies"></a>ベースラインポリシーを設定する

1. [Azure portal](https://portal.azure.com)に移動して、 **azure Active Directory** \>の**条件付きアクセス**に移動します。
    
    ベースラインポリシーがページに一覧表示されます。 <br/> <br/>
    ![条件付きアクセスのベースラインポリシーを一覧表示するページ。](media/baslinepolicies.png)
1. 各ポリシーについて、次の具体的な手順を参照してください。

    - [管理者に MFA を要求する](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)

    -   [ユーザーに MFA を要求する](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [従来の認証をブロックする](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)

承認済みのクライアントアプリの要求など、多くの追加のポリシーを設定できます。 詳細については、[条件付きアクセスのドキュメント](https://docs.microsoft.com/azure/active-directory/conditional-access/)を参照してください。