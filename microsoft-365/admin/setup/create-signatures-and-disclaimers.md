---
title: 組織全体の署名と免責事項を作成する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 組織で受信または退出する電子メール メッセージの法的免責事項や開示声明など、電子メールの署名を管理する方法について説明します。
ms.openlocfilehash: c8d63a11a75b9b53de9cabdf1f4baabc61cc3e42
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926920"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>組織全体の署名と免責事項を作成する

 電子メールの署名を管理するには、組織に入退出する電子メール メッセージに電子メール署名、法的免責事項、または開示ステートメントを追加します。 以下に示すように、すべての送受信メッセージに適用されるように設定できます。 または、特定の単語やテキスト パターンを含むメッセージなど、特定のメッセージに適用することができます。

 会社全体の電子メール署名の作成に関する短いビデオをご覧ください。 <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

## <a name="create-a-signature-that-applies-to-all-messages"></a>すべてのメッセージに適用される署名を作成する

> [!TIP]
> 組織全体の署名は、何が含まれるかにかかわらず、"免責事項" と呼ばれる。 たとえば、単に署名にしたり、住所、法的免責事項、その他の必要な情報を含む場合があります。
    
::: moniker range="o365-worldwide"

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-germany"

<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> から管理センターにアクセスします。

::: moniker-end

1. アプリ起動ツールの ![ [アプリ起動ツール] アイコンを選択し、[管理] ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) を **選択します**。
   
    お探しのアプリが見つかりませんか? アプリ起動ツールから [すべてのアプリ] を **選択** すると、利用できるアプリのアルファベット順の一覧が表示されます。 そこから、特定のアプリを検索できます。 
    
2. [管理 **センター] を** 選択し **、[Exchange] を選択します**。
    
3. [メール フロー] で、[ルール] を **選択します**。
    
4. (追加 **+** ) アイコンを選択し、[免責事項の適用 **] を選択します**。
    
5. ルールに名前を付けます。
    
6. [ **このルールを適用する] で**、[ **すべてのメッセージに適用] を選択します**。
    
    > [!TIP]
    > [こちら](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)を参照してください。 (この範囲に関する記事はExchange Server対象ですが、Microsoft 365 にも適用されます)。 
  
7. [実行する処理] の [ **免責事項を追加する**] はオンのままにします。 
    
8.  [テキスト **の入力] を選択** し、免責事項を入力します。 
    
    > [!TIP]
    > [免責事項の書式設定の詳細](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)をご確認ください。 (この書式設定に関する記事Exchange Server、Microsoft 365 にも適用されます)。 

9. Select **one and** choose **Wrap** as a fallback option. [ **OK**] を選択します。 これは、暗号化や別のメール設定のために免責事項を追加できない場合に、メッセージ エンベロープで免責事項がラップされることを意味します。
    
10. [ **このルールを次の重大度レベルで監査する**] はオンのままにします。次に、メッセージ ログに使用する [ **低**]、[ **中**]、または [ **高**] を選択します。 
    
11. 先にテストしない場合は、[ **強制**] を選択して免責事項を即時に有効にします。 
    
12. 追加の条件や例外を含めるには、[ **その他のオプション**] を選択します。 
    
13. 完了したら、[ **保存**] を選択します。 
    
## <a name="limitations-of-organization-wide-signatures"></a>組織全体の署名の制限事項

Microsoft 365 でメール署名を管理する場合、次の操作を行う必要があります。
  
- 最新のメール返信または転送の下に署名を直接挿入する
    
- ユーザーの送信アイテム フォルダーにサーバー側の電子メール署名を表示する
    
- メール署名に画像を埋め込む
    
- 更新できなかった変数を含む行をスキップする (たとえば、値がユーザーに提供できなかったため)
    
電子メール署名を管理するためのこれらの機能や他の機能を利用するには、サード パーティ製のツールを使用します。 Please do an internet search for **email signature software**. これらのプロバイダーの多くが Microsoft ゴールド パートナーであり、そのソフトウェアがこれらの機能を提供します。 
  
## <a name="more-resources"></a>その他のリソース

- PowerShell [の使用については、Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) の組織全体のメッセージ免責事項、署名、フッター、またはヘッダーを参照してください。