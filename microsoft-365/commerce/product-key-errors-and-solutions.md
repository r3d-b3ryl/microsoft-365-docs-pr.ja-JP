---
title: Microsoft 365 for business プロダクトキーに関する問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 88d337ab-e7b1-43eb-a25e-7d6204e91099
ROBOTS: NOINDEX
description: 'Microsoft 365 for business のプロダクトキーを入力したときに発生する問題を解決する方法について説明します。 '
ms.custom:
- okr_SMB
- AdminSurgePortfolio
ms.openlocfilehash: dd3ac00061d1e509dddbc83c8ba3c4631100b63e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818649"
---
# <a name="problems-with-your-microsoft-365-for-business-product-key"></a>Microsoft 365 for business プロダクトキーに関する問題

**Microsoft 365 for business**のプロダクトキーの償還を試行するときにエラーメッセージが表示される場合は、次の一般的なソリューションを試してみてください。 
  
 **すぐにヘルプが必要な場合** [Microsoft サポートにお問い合わせ](../admin/contact-support-for-business-products.md)ください。 
  
 **Microsoft 365 ファミリまたは microsoft 365 の個人プロダクトキー**に関するヘルプについては、「 [Office でプロダクトキーを使用する](https://support.microsoft.com/office/12a5763a-d45c-4685-8c95-a44500213759.aspx)」を参照してください。
  
## <a name="product-key-error-help-with-microsoft-365-for-business"></a>Microsoft 365 for business のプロダクトキーのエラーのヘルプ

| プロダクト キーを入力したときに表示されるエラー メッセージ | 実行する操作 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| "申し訳ございません。このプロダクトキーは無効です。 もう一度入力してください。 プロダクトキーが Microsoft 365 Personal または Microsoft 365 ファミリの場合は、office.com/setup にご利用ください。 <br/><br/>日本で Office 365 ソロを使用している場合: "申し訳ございません。このプロダクトキーは無効です。 もう一度入力してください。 プロダクトキーが Office 365 ソロの場合は、office.com/setup でお客様にご利用ください。 | [Microsoft 365 ファミリまたは個人](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx)を設定している場合は、でプロダクトキーを使用する必要があり [https://www.office.com/setup](https://www.office.com/setup) ます。 一般法人のお客様の場合は、入力する数字と文字を慎重に確認してください。 |
| "The product key you entered isn't valid. Try entering it again." Or "This product key isn't valid. Please enter a different product key." | Carefully check the numbers and characters you are entering. Mistakes can be made with 0 and o, 5 and S, l and I, and so on. If the issue persists, please contact the reseller where you bought your product key. |
| "You have already entered this product key. Enter a different key." | Check the product keys you already entered to see if the key has already been added. If you are renewing a subscription using a product key, you must use a new and unused product key. <br/><br/>Need to buy a new key? Visit the [Microsoft Store](https://go.microsoft.com/fwlink/p/?LinkId=529160) or a third-party reseller, or—if you're working with a partner—contact your partner. <br/><br/>問題が解決しない場合は、[サポートにお問い合わせ](../admin/contact-support-for-business-products.md)ください。 パートナーと契約している場合は、パートナーに連絡して、プロダクト キーのサポートを受けてください。 |
| "The product key you entered has expired. Enter a different key." | 現在のサブスクリプションを更新するか、新しいサブスクリプションをアクティブにするには、新しい未使用のプロダクト キーを使用する必要があります。<br/><br/>Need to buy a new key? Visit the [Microsoft Store](https://go.microsoft.com/fwlink/p/?LinkId=529160) or a third-party reseller, or—if you're working with a partner—contact your partner. |
| "This product key has already been used. Please enter a different product key." | Verify that the key hasn't already been used by you or a member of your organization. If the key hasn't already been used, please contact your partner or the reseller where you bought the product key. |
| "Sorry, we can't process your request right now. Please wait a few minutes and try again." | 15分以上後に同じエラーメッセージが表示される場合は、[サポートにお問い合わせ](../admin/contact-support-for-business-products.md)ください。 |
| "The requested subscription is not available. One of the following reasons could have caused this: The offer is not available - The service is not available in your country - It is impossible to use/select the same trial twice. If the issue persists, contact Microsoft support." | [サポートにお問い合わせ](../admin/contact-support-for-business-products.md)ください。 パートナーと契約している場合は、パートナーに連絡して、サポートを受けてください。 |
| "このオファーより多くのユーザーライセンスが追加されています。 最大数は \<x\> ユーザーライセンスです。 このプロダクトキーを削除して、追加するユーザーライセンスの数を減らします。 | 販売店またはパートナーに問い合わせてください。 この Microsoft 365 サブスクリプションで使用できるライセンス数を超えるライセンスを購入しています。 |
| "プロダクト キーを使うには全体管理者または課金管理者でなければいけません。" | アクセス許可が課金またはグローバル管理者のどちらかに設定されていることを確認してください。これを確認するには、職場または学校のアカウントを使用して[Microsoft 365 にサインイン](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)し、管理センターに移動します。 <br/><br/>In the admin center, select **Users** \> **Active users**. In **Filters**, choose **Global admins** or **Billing admins**. <br/><br/>結果の一覧に表示されていることを確認します。 |
   
> [!NOTE]
> パートナーを通じて Microsoft 365 を購入すると、プロダクトキーを取得して、[ボリュームライセンスサービスセンター](https://go.microsoft.com/fwlink/p/?LinkID=282016)でサブスクリプションのライセンス認証を行うための手順が記載された電子メールが microsoft から送信されます。 ボリューム ライセンスの詳細については、「[既存のボリューム ライセンスのお客様のヘルプ](https://go.microsoft.com/fwlink/p/?LinkId=534992)」を参照してください。 
  
## <a name="related-articles"></a>関連記事

[プロダクトキーを検索して入力する](enter-your-product-key.md)
  
[サブスクリプションを更新する](subscriptions/renew-your-subscription.md)
  
[サブスクリプションのライセンスを購入する](licenses/buy-licenses.md)
