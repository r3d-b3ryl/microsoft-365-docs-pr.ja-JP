---
title: 課金プロファイルを理解する
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: amberb, vikdesai
audience: Admin
ms.topic: article
f1.keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: 課金プロファイルが請求書をサポートする方法について説明します。
ms.date: 04/02/2021
ms.openlocfilehash: 92c8bd302d65bc9f7c9376ac148fd49a0ac18e04
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102550"
---
# <a name="understand-billing-profiles"></a>課金プロファイルを理解する

課金プロファイルには、支払い方法、請求先情報、その他の請求書設定 (発注書番号、電子メール請求書の設定など) が含まれています。 課金プロファイルを使用して、Microsoft から購入した製品の料金を支払います。 課金プロファイルは、ユーザーがセルフサービスで購入したときに自動的に作成されます。 各課金プロファイルは個別に請求されます。

> [!NOTE]
>
> 課金プロファイルは、Microsoft.com またはMicrosoft 365 管理センターの **[サービスの購入**] ページで製品やサービスを購入する顧客には使用できません。

## <a name="what-are-billing-profile-roles"></a>課金プロファイル ロールとは何ですか?

課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。 請求書を追跡、整理、支払うユーザーにこれらのロールを割り当てます。 たとえば、組織内の調達チームのメンバーなどです。

| 役割                         | 説明                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| 課金プロファイルの所有者        | 課金プロファイルのすべてを管理する                                          |
| 課金プロファイル共同作成者  | 課金プロファイルのアクセス許可を除くすべてを管理する                        |
| 課金プロファイル リーダー       | 課金プロファイル内のすべての情報の読み取り専用ビュー                                |
| 請求書マネージャー              | 請求書を表示および支払いし、課金プロファイル内のすべての情報を読み取り専用で表示する  |

## <a name="view-my-billing-profiles"></a>課金プロファイルを表示する

> [!NOTE]
>
> これらの手順に従い、課金プロファイルの一覧が空の場合は、課金プロファイルがなく、この機能を使用できないことを意味します。

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。
2. **[ 課金プロファイル]** タブを選択し、一覧から課金プロファイルを選択します。

各課金プロファイルには、次の情報が含まれます。

- **課金プロファイルの名前と状態** &ndash; 課金プロファイルの一意の名前、および課金プロファイルが購入に対してアクティブか無効かを指定します。
- **請求書の設定** &ndash; 課金アカウントの国、請求書の頻度と日付に関する情報、電子メールの添付ファイルとして請求書を受け取るオプション、オプションの PO 番号フィールドに基づく通貨
- **支払い方法** &ndash; プロファイルのプライマリとバックアップの支払い方法 (存在する場合) を表示します。
- **課金アカウント** &ndash; プロファイルが関連付けられている課金アカウントの名前。 課金アカウントの詳細については、「 [課金アカウントについて](../manage-billing-accounts.md)」を参照してください。
-  &ndash;連絡先情報請求先住所と連絡先の名前と電子メール アドレス
- **課金プロファイル ロール** &ndash; そのプロファイルに対して実行する課金プロファイル ロールの 1 つを割り当てられているユーザーの一覧。 たとえば、請求書の支払い、PO 番号の追加、購入に使用される支払い方法の置き換えなどです。

> [!NOTE]
>
> 課金プロファイル ロールは、組織内のユーザーにのみ割り当てることができます。

## <a name="need-help-contact-support"></a>お困りの際は、 サポートにお問い合せください

Azure の料金に関する質問やサポートが必要な場合は、<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Azure サポートでサポート リクエストを作成</a>します。

Microsoft 365 管理センターで課金プロファイルに関する質問やヘルプが必要な場合は、[サポートにお問い合わせください](../../admin/get-help-support.md)。

## <a name="related-content"></a>関連コンテンツ

[課金プロファイルを使用してサブスクリプションに対して支払う方法](pay-for-subscription-billing-profile.md) (記事)\
[課金アカウントについて (](../manage-billing-accounts.md) 記事)\
[支払い方法の管理](manage-payment-methods.md) (記事)
