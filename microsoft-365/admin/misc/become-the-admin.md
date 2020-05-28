---
title: 内部管理者の引き継ぎを実行する
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
description: Microsoft 365 で管理されていないテナントを電子メールとドメインの所有権を引き継ぐために確認する方法について説明します。
ms.openlocfilehash: 4c2dcdb0f6c4f6b795d9579c8796e9668ed2ed05
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399448"
---
# <a name="perform-an-internal-admin-takeover"></a>内部管理者の引き継ぎを実行する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 

管理者が、セルフサービスユーザーサインアップによって作成された管理されていないテナントを引き継ぐ場合は、内部管理者の引き継ぎを使用してこれを行うことができます。

> [!NOTE]
> Azure AD を使用するすべてのクラウドサービスに対してセルフサービスサインアップを行うと、非管理対象または "シャドウ" Azure AD ディレクトリにユーザーが追加され、管理されていないテナントが作成されます。 管理されていないテナントは、全体管理者のいないディレクトリです。 テナントが管理されているかどうかを判断するには、「[テナントの種類を決定](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)する」を参照してください。 
  
## <a name="step-1-verify-your-email-address"></a>手順 1: メールアドレスを確認する

> [!NOTE]
> テナントでセルフサービスが有効になっている場合、ユーザーは Power BI などの無料のサービスを独自にサブスクライブできます。 次の手順では、セルフサービスのユーザーサブスクリプションが管理者として引き継がれる非管理対象テナントを作成したと仮定します。最初の手順では、管理されていないテナントでユーザーコンテキストを作成し、Power BI を使用して管理者の引き継ぎパスを示します。

1. Power bi にサインアップするには、 [power bi サイト](https://powerbi.com)に移動して、[**無料**  >  **試用版**の開始] ([power bi Pro と共有] ボックス) を選択します。 

2. 組織のドメイン名 (など) を使用するユーザーアカウントでサインアップ `powerbiadmin@contoso.com` します。 アカウントが既に使用されている場合は、現在のパスワードを使用してサインインします。

3. **確認コード**の電子メールを確認し、電子メールアドレスを検証するコードを入力します。
    
## <a name="step-2-create-a-new-account"></a>手順 2: 新しいアカウントを作成する

1. 確認コードを入力すると、新しいアカウントを作成できるページが表示されます。 
    
2. ユーザー名とパスワードのフィールドに、使用するアカウントを入力し、[**開始**] を選択します。 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a>手順 3: ドメインの所有権を確認し、管理者になる

1. [**管理者になる**] ウィザードが開きます。 ウィザードが開始されない場合は、[**管理者**] タイルを探して選択します。 

2. [**はい、管理者にする]** を選択します。

3. TXT レコードをドメインレジストラーに追加することによって、引き継ぎたいドメインを所有していることを確認します。 ウィザードによって、追加する TXT レコードが提供されます。また、レジストラーの web サイトへのリンクと、ステップごとの手順へのリンクも提供します。
    
4. レジストラーサイトに TXT レコードを追加したら、ウィザードに戻り、[Ok] を選択して、**レコードを追加**しました。
    
> [!NOTE]
> シャドウテナントを引き継ぐことは、既存の情報やサービスに影響を与えることはありません。 ただし、ドメイン内のユーザーがライセンスを必要とするサービスにサインアップしている場合は、管理者の役割を引き継ぐ際にライセンスを購入するように求められます。 管理者セットアッププロセスが完了すると、ライセンスを追加または削除することができます。 
  
## <a name="related-articles"></a>関連記事

YouTube: [POWER BI および Microsoft 365 に関して IT 管理者を引き継ぐための3つの手順](https://www.youtube.com/watch?v=xt5EsrQBZZk)

[Azure AD での管理の引き継ぎ](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[ドメインに関するヘルプを取得する](../get-help-with-domains/get-help-with-domains.md)

[組織でのセルフサービスサインアップの使用](self-service-sign-up.md)
  
[Power BI サービス管理者の役割について](https://docs.microsoft.com/power-bi/service-admin-role)

