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
ms.localizationpriority: medium
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
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: 組織に出入りするすべての電子メール メッセージの法的免責事項や開示声明など、電子メール署名を管理します。
ms.openlocfilehash: 47e6a862441b5c2725a48cae20669541b8a69f87
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66602814"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>組織全体の署名と免責事項を作成する

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

 電子メール署名を管理するには、電子メール署名、法的免責事項、または開示に関する声明を、組織に出入りする電子メール メッセージに追加します。 以下に示すように、すべての送受信メッセージに適用されるように設定できます。 または、特定の単語やテキスト パターンを含むメッセージなど、特定のメッセージに適用することができます。

## <a name="watch-create-a-company-wide-email-signature"></a>ウォッチ: 組織全体の電子メール署名を作成する
  
[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2198031)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>で **Exchange を選択** します。
1. [ **メール フロー**] を選択します。
1. [ **+]** を選択し、[ **免責事項の適用**] を選択します。
1. [ **新しいルール** ] ページで、手順を完了します。 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../../business-video/index.yml)」をご覧ください。

## <a name="create-a-signature-that-applies-to-all-messages"></a>すべてのメッセージに適用される署名を作成する

> [!TIP]
> 組織全体の署名は、含まれるものに関係なく、"免責事項" と呼ばれます。 たとえば、署名にしたり、住所、法的免責事項、または必要なその他の情報を含めたりすることもできます。
    
::: moniker range="o365-worldwide"

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

::: moniker-end

::: moniker range="o365-21vianet"

<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a> から管理センターにアクセスします。

::: moniker-end

1. アプリ起動ツール![の [アプリ起動ツール] アイコンを](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)選択し、**管理** を選択します。
   
    お探しのアプリが見つかりませんか? アプリ起動ツールから [ **すべてのアプリ** ] を選択すると、使用可能なアプリのアルファベット順の一覧が表示されます。 そこから、特定のアプリを検索できます。 
    
2. **管理センター** を選択し、**Exchange** を選択します。
    
3. [メール フロー] で [ルール] を選択 **します**。
    
4. (追加) アイコンを **+** 選択し、[ **免責事項の適用**] を選択します。
    
5. ルールに名前を付けます。
    
6. [ **このルールを適用**] で **[すべてのメッセージに適用**] を選択します。
    
    > [!TIP]
    > [こちら](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping)を参照してください。 (このスコープの記事はExchange Server用ですが、Microsoft 365 にも適用されます)。 
  
7. [実行する処理] の [ **免責事項を追加する**] はオンのままにします。 
    
8.  [ **テキストの入力** ] を選択し、免責事項を入力します。 
    
    > [!TIP]
    > [免責事項の書式設定の詳細](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer)をご確認ください。 (この書式設定の記事はExchange Server用ですが、Microsoft 365 にも適用されます)。 

9. **1 つを選択** し、[フォールバックとして **折り返す**] オプションを選択します。 [ **OK**] を選択します。 これは、暗号化や別のメール設定のために免責事項を追加できない場合に、メッセージ エンベロープで免責事項がラップされることを意味します。
    
10. [ **このルールを次の重大度レベルで監査する**] はオンのままにします。次に、メッセージ ログに使用する [ **低**]、[ **中**]、または [ **高**] を選択します。 
    
11. 先にテストしない場合は、[ **強制**] を選択して免責事項を即時に有効にします。 
    
12. 追加の条件や例外を含めるには、[ **その他のオプション**] を選択します。 
    
13. 完了したら、[ **保存**] を選択します。 
    
## <a name="limitations-of-organization-wide-signatures"></a>組織全体の署名の制限事項

Microsoft 365 で電子メール署名を管理する場合は、次の操作を行うことはできません。
  
- 最新のメール返信または転送の下に署名を直接挿入する
    
- ユーザーの送信済みアイテム フォルダーにサーバー側の電子メール署名を表示する
    
- 電子メール署名に画像を埋め込む
    
- 更新できなかった変数を含む行をスキップする (たとえば、値がユーザーに指定されなかったため)
    
これらの機能やその他の機能を利用して電子メール署名を管理するには、サード パーティのツールを使用します。 **電子メール署名ソフトウェア** のインターネット検索を行ってください。 これらのプロバイダーの多くは Microsoft Gold パートナーであり、そのソフトウェアはこれらの機能を提供します。 
  
## <a name="more-resources"></a>その他のリソース

PowerShell の使用の詳細については、[Exchange Onlineの組織全体のメッセージの免責事項、署名、フッター、またはヘッダーに関するページを](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)参照してください。

## <a name="related-content"></a>関連コンテンツ

[電子メールと連絡先を Microsoft 365 に移行する](migrate-email-and-contacts-admin.md) (ビデオ)\
[ユーザーの電子メール設定](../email/office-365-user-email-settings.md) (記事)\
[Microsoft 365 管理センターの概要](Microsoft 365 管理センターの概要](../admin-overview/admin-center-overview.md) (ビデオ)

