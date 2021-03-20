---
title: 内部管理者の引き取りを実行する
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Microsoft 365 で管理されていないテナントを引き継ぐ電子メールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: 72278fd0e373848a79f9823e186b19bc1cb47770
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914848"
---
# <a name="perform-an-internal-admin-takeover"></a>内部管理者の引き取りを実行する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 

管理者であり、セルフサービス ユーザーサインアップによって作成された管理されていないテナントを引き継ぐ場合は、内部管理者の引き継ぎでこれを行います。

> [!NOTE]
> Azure AD を使用するクラウド サービスにセルフサービスでサインアップすると、ユーザーは管理されていないまたは "シャドウ" な Azure AD ディレクトリに追加され、管理されていないテナントが作成されます。 管理されていないテナントは、グローバル管理者のないディレクトリです。 テナントが管理されているかどうかを確認するには、「テナントの種類の決定」 [を参照してください](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>手順 1: メール アドレスを確認する

> [!NOTE]
> テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分でサブスクライブできます。 これらの手順では、セルフサービス ユーザー サブスクリプションによって管理者として引き継ぐ管理されていないテナントが作成されたと仮定します。最初の手順では、管理されていないテナントにユーザー コンテキストを作成し、Power BI を使用して管理者の引き継ぎパスを説明します。

1. Power BI にサインアップするには[、Power BI](https://powerbi.com)サイトに移動し、[無料開始無料試用版の開始] ([Power BI Pro と共有] ボックス)  >  を選択します。 

2. 組織のドメイン名 (など) を使用するユーザー アカウントにサインアップします `powerbiadmin@contoso.com` 。 アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。

3. 確認コードをメールで確認 **し、** メール アドレスを検証するコードを入力します。
    
## <a name="step-2-create-a-new-account"></a>手順 2: 新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページに移動します。 
    
2. 使用するアカウントでユーザー名とパスワードフィールドを入力し、[スタート] を選択 **します**。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. [ **管理者になる] ウィザード** が開きます。 ウィザードが起動しない場合は、管理タイルを **探して** 選択します。 

2. [ **はい] を選択します。管理者になる必要があります**。

3. ドメイン レジストラーに TXT レコードを追加して、引き継ぐドメインを所有している必要があります。 ウィザードは、追加する TXT レコードを提供し、レジストラーの Web サイトへのリンクと、詳細な手順へのリンクを提供します。
    
4. レジストラー サイトに TXT レコードを追加したら、ウィザードに戻り、[大丈夫] を選択します。レコード **を追加しました**。
    
> [!NOTE]
> シャドウ テナントを引き継ぐと、既存の情報やサービスに影響はありません。 ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者ロールの引き継ぎの一環として、ライセンスの購入を求めるメッセージが表示されます。 管理者のセットアップ プロセスが完了したら、ライセンスを購入または削除できます。
  
## <a name="related-articles"></a>関連記事

YouTube: Power BI と[Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)の IT 管理者の引き取りを行う 3 つの手順

[Azure の管理者の引き取りAD](/azure/active-directory/users-groups-roles/domains-admin-takeover)

[組織でのセルフサービス サインアップの使用](self-service-sign-up.md)
  
[Power BI Service 管理者の役割について](/power-bi/service-admin-role)