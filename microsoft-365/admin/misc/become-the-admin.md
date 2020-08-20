---
title: 内部管理者のイークバーを実行する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Microsoft 365 の管理されていないテナントを経由するメールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: 9c1d98616b10737553060bcbad62df9b3b4c0c9a
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814470"
---
# <a name="perform-an-internal-admin-takeover"></a>内部管理者のイークバーを実行する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 

管理者がセルフサービス ユーザー サインアップによって作成された非管理対象テナントを置き継いき、内部管理者のイールでこれを実行できます。

> [!NOTE]
> Azure AD を使用する任意のクラウド サービスにセルフサービス サインアップすると、管理されていないテナントまたは "シャドウ" の Azure AD ディレクトリにユーザーが追加され、管理されていないテナントが作成されます。 非管理対象テナントは、グローバル管理者が存在しないディレクトリです。 テナントが管理対象か非管理対象かを判断するには、「テナントの [種類の決定」を参照してください](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>手順 1: メール アドレスを確認する

> [!NOTE]
> テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分で購読できます。 この手順では、セルフサービス ユーザーのサブスクリプションで管理対象の管理対象のないテナントが作成されていると想定しています。最初の手順では、管理されていないテナントでユーザー コンテキストを作成し、Power BI を使用して管理者の選択取り込みパスを示します。

1. Power BI にサインアップするには、Power BI サイトに**Start Free**[移動して、[無料](https://powerbi.com)のスタート画面一覧で (Power BI Pro で共有する]  >  **Start free trial**ボックスで) [無料のスタート画面を使い始めにする] を選択します。 

2. 組織のドメイン名を使用するユーザー アカウント (例: `powerbiadmin@contoso.com` アカウントが既に使用されている場合は、現在のパスワードを使ってサインインします。

3. メールで確認コードを **確認し、** メール アドレスを検証するコードを入力します。
    
## <a name="step-2-create-a-new-account"></a>手順 2: 新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページが表示されます。 
    
2. ユーザー名フィールドとパスワード フィールドに使用するアカウントを入力し、[スタート] を選択 **します**。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. [ **管理者になる] ウィザード** が開きます。 ウィザードが開始されない場合は、[管理者] タイル **を見つ** け、選択します。 

2. Select **Yes, I want to be the admin.**

3. TXT レコードをドメイン レジストラーに追加して、自分が管理するドメインを所有していることを確認します。 ウィザードから追加する TXT レコードが表示されます。また、レジストラーの Web サイトへのリンクと手順のリンクも表示されます。
    
4. テレナー サイトに TXT レコードを追加したら、ウィザードに戻り **、[OK] を選択すると、レコードが追加されました**。
    
> [!NOTE]
> シャドウ テナントを引き続き取りても、既存の情報やサービスには影響はありません。 ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者ロールを取得する一部として、それらのユーザーのライセンスを購入する必要があります。 管理者セットアップ プロセスが完了したら、ライセンスを購入するか、削除できます。
  
## <a name="related-articles"></a>関連記事

YouTube: [Power BI と Microsoft 365 で IT 管理者のイーオーバーを行う 3 つの手順](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure 管理センターでの管理者のAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[組織でのセルフサービス サインアップの使用](self-service-sign-up.md)
  
[Power BI サービス管理者の役割について](https://docs.microsoft.com/power-bi/service-admin-role)

