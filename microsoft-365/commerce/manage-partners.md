---
title: ソリューションプロバイダーを操作する
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: Microsoft 認定のソリューションプロバイダーと協力して、組織または学校の製品とサービスを購入して管理することができます。
keywords: パートナー、ソリューションプロバイダ
ms.openlocfilehash: bb78e1a704529fd2d12ff49639913fe80b75be7a
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994078"
---
# <a name="working-with-solution-providers-in-microsoft-store-for-business"></a>ビジネス向け Microsoft Store のソリューションプロバイダーを使用する

Microsoft 認定のソリューションプロバイダーと協力して、組織または学校の製品とサービスを購入して管理することができます。 設定を行うには、いくつかの手順が必要になります。 

プロセスは次のようになります。
- 管理者は、Microsoft Store for Business で [**ソリューションプロバイダーの検索**] を使用してソリューションプロバイダーを検索し、そのプロバイダーに連絡します。 
- ソリューションプロバイダーは、パートナーセンターからお客様のソリューションプロバイダになる要求を送信します。
- お客様は、Microsoft Store for Business の招待を承諾し、ソリューションプロバイダの使用を開始します。
- お客様は、Microsoft Store for Business のパートナーとの関係の設定を管理できます。 

## <a name="what-can-a-solution-provider-do-for-my-organization-or-school"></a>組織または学校のソリューションプロバイダーには、どのようなものがありますか?

ソリューションプロバイダーは、いくつかの方法で作業できます。 ソリューションプロバイダーは、パートナーとして機能するために要求を送信するときに、これらのいずれかを選択します。

| ソリューションプロバイダ関数 | 説明 | 
| ------ | ------------------- | 
| 問い合わせ | ソリューションプロバイダーは、組織または学校に Microsoft 製品を販売しています。 |
| 代理管理者 | ソリューションプロバイダは、組織または学校の製品とサービスを管理します。 Azure Active Directory (AD) では、パートナーはテナントのグローバル管理者になります。 これにより、ユーザーアカウントの作成、ライセンスの割り当てと管理、パスワードのリセットなどのサービスを管理することができます。 |
| 販売店 & 代理管理者 | 組織または学校への Microsoft 製品とサービスを販売および管理するソリューションプロバイダー。 |
| パートナー | ソリューションプロバイダーにテナントのユーザーアカウントを提供し、他の Microsoft サービスに代わって作業することができます。 |
| Microsoft 製品 & サービス契約 (MPSA) パートナー | MPSA プログラムを使用して複数のソリューションプロバイダーを使用した場合、パートナーが相互に購入したものを確認できるようにすることができます。 |
| OEM PC パートナー | ソリューションプロバイダーは、[自動操縦を使用して管理](https://docs.microsoft.com/microsoft-store/add-profile-to-devices)している pc のデバイス id をアップロードできます。   |
| 基幹業務 (LOB) パートナー | ソリューションプロバイダーは、組織または学校に固有の LOB アプリを開発、提出、および管理できます。 |

## <a name="find-a-solution-provider"></a>ソリューションプロバイダーを検索する

ビジネスおよび教育機関向けの Microsoft Store には、パートナーを見つけることができます。 

1. 教育機関向け[Microsoft store For Business](https://businessstore.microsoft.com/)または[microsoft store](https://educationstore.microsoft.com/)にサインインします。
2. [**ソリューションプロバイダーの検索**] を選択します。
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-find-partner.png)
-->
3. リストを絞り込むか、ソリューションプロバイダーを検索します。 
<!---
    ![Image shows Find a solution provider option in Microsoft Store for Business.](images/msfb-provider-list.png)
-->
4. 作業を希望するソリューションプロバイダーが見つかったら、[**連絡先**] をクリックします。
5. フォームを完成させ、送信します。

ソリューションプロバイダーは、ユーザーと連絡を取ります。 詳細については、こちらを参照してください。 ソリューションプロバイダーを使用して作業する場合は、パートナーセンターから電子メール招待状を送信します。 

## <a name="work-with-a-solution-provider"></a>ソリューションプロバイダーを操作する

ソリューションプロバイダーを見つけて、それを使用することにした場合は、パートナーセンターから共同で作業するための招待状が送信されます。 Business または教育機関向け Microsoft Store では、招待状を承諾する必要があります。 その後、アクセス許可を管理できます。

**ソリューションプロバイダーへの招待を承諾するには**
1. [**電子メールのフォロー] リンク**-ソリューションプロバイダーからソリューションプロバイダへの招待を受け入れるためのリンクを含む電子メールを受信します。 このリンクにより、ビジネスまたは教育機関向け Microsoft Store に移動します。
2. **招待を承諾**する-[**パートナーへの招待を承諾**する] で、[**承認**] を選択して招待状を承諾し、Microsoft Cloud Agreement の条項に同意して、ソリューションプロバイダーの作業を開始します。 
<!---
![Image shows accepting an invitation from a solution provider in Microsoft Store for Business.](images/msft-accept-partner.png)
--> 
## <a name="delegate-admin-privileges"></a>管理者権限を委任する

ソリューションプロバイダーによる要求に応じて、招待の承諾の一部として、委任された管理者権限をソリューションプロバイダーに付与することが同意されます。 これは、ソリューションプロバイダ要求が代理管理者として機能する場合に発生します。 詳細については、「 [AZURE AD での管理者権限の委任](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)」を参照してください。 

管理者特権をソリューションプロバイダーに委任しない場合は、招待を承諾するのではなく、キャンセルする必要があります。 

管理者特権をソリューションプロバイダーに委任する場合は、後で削除できます。 

**代理人の管理者権限を削除するには**
1. 教育機関向け[Microsoft store For Business](https://businessstore.microsoft.com/)または[microsoft store](https://educationstore.microsoft.com/)にサインインします。
2. **パートナー**の選択
3. 管理するパートナーを選びます。
4. [委任された**アクセス許可の削除**] を選択します。 

ソリューションプロバイダーは、たとえば、販売店として作業することができます。 
