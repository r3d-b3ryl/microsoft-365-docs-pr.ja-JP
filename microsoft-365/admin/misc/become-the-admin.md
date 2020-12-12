---
title: 内部管理者の引き受け取りを実行する
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
description: Microsoft 365 で管理されていないテナントを引き継ぐメールとドメインの所有権を確認する方法について説明します。
ms.openlocfilehash: 28359908576260218459d13b8c1c1b662b9a2c8f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658065"
---
# <a name="perform-an-internal-admin-takeover"></a>内部管理者の引き受け取りを実行する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.yml)** を参照してください。 

管理者であり、セルフサービス ユーザーサインアップによって作成された管理されていないテナントを引き継ぐ場合は、内部管理者の引き継ぎを使用してこれを行います。

> [!NOTE]
> Azure AD を使用するクラウド サービスのセルフサービス サインアップでは、ユーザーが管理されていない Azure AD ディレクトリまたは "シャドウ" ディレクトリに追加され、アンマネージ テナントが作成されます。 管理されていないテナントは、グローバル管理者が存在しないディレクトリです。 テナントが管理されているかどうかを判断するには、「テナントの種類の決定」を [参照してください](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。 
  
## <a name="step-1-verify-your-email-address"></a>手順 1: メール アドレスを確認する

> [!NOTE]
> テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料サービスを自分で購読できます。 これらの手順では、セルフサービス ユーザー サブスクリプションによって、管理者として引き継ぐ管理されていないテナントが作成されたと想定しています。最初の手順では、管理されていないテナントにユーザー コンテキストを作成し、Power BI を使用して管理者の引き継ぎパスを示します。

1. Power BI にサインアップするには[、Power BI](https://powerbi.com)サイトに移動し、[無料スタート無料試用版を開始する] を選択します (Power BI Pro と共有  >  するボックス)。 

2. 組織のドメイン名 (例: ) を使用するユーザー アカウントでサインアップします `powerbiadmin@contoso.com` 。 アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。

3. メールで確認コードを **確認し、** メール アドレスを検証するコードを入力します。
    
## <a name="step-2-create-a-new-account"></a>手順 2: 新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページが表示されます。 
    
2. 使用するアカウントをユーザー名とパスワードのフィールドに入力し、[スタート] を選択 **します**。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. [ **管理者になる] ウィザード** が開きます。 ウィザードが開始しない場合は、[管理] タイル **を探して** 選択します。 

2. Select **Yes, I want to be the admin**.

3. TXT レコードをドメイン レジストラーに追加して、引き継ぐドメインを所有している必要があります。 ウィザードによって、追加する TXT レコードが表示されます。また、レジストラーの Web サイトへのリンクと、詳しい手順へのリンクも提供されます。
    
4. TXT レコードをレジストラー サイトに追加したら、ウィザードに戻り **、[Okay, I've added the record**.
    
> [!NOTE]
> シャドウ テナントを引き継ぐと、既存の情報やサービスに影響を与える可能性はありません。 ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者ロールの引き継ぎの一環としてライセンスを購入する必要があります。 管理者のセットアップ プロセスが完了したら、ライセンスを購入または削除できます。
  
## <a name="related-articles"></a>関連記事

YouTube: Power BI と[Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)の IT 管理者の引き受け取りを行う 3 つの手順

[Azure AD での管理者の引きAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[組織でのセルフサービス サインアップの使用](self-service-sign-up.md)
  
[Power BI サービス管理者の役割について](https://docs.microsoft.com/power-bi/service-admin-role)

