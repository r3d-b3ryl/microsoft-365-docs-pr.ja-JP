---
title: EOP スタンドアロンで迷惑メールをブロックする
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 2/25/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: da21c0b6-e8f0-4cc8-af2e-5029a9433d59
ms.collection:
- M365-security-compliance
description: Office 365 スパム対策フィルターを構成して迷惑メールをブロックし、検出漏れメッセージを防ぐ方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16bb5530384dba360483eba3a8e05fbfdf3fe895
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035582"
---
# <a name="customize-the-anti-spam-filter-with-these-settings"></a>以下の設定によりスパム対策フィルターをカスタマイズする

管理者は、いくつかのスパム フィルターの設定を利用して、迷惑メールがユーザーの受信トレイに送信されないようにすることができます。この一覧のオプションを使用すると、スパム フィルターは、より適切に迷惑メールをブロックし、検出漏れのメッセージを防ぐことができるようになります。このコンテキストでは、検出漏れとは、ユーザーの受信トレイに送信されてしまうスパム メールや迷惑メッセージのことです。

## <a name="block-ip-addresses-with-a-connection-filter"></a>接続フィルターで IP アドレスをブロックする

接続フィルター IP 禁止一覧に送信者の IP アドレスを追加して、スパム フィルターをカスタマイズします。

1. 「[Outlook のインターネット メッセージ ヘッダーの表示](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)」で説明されているように、Outlook や Outlook on the web (以前の Outlook Web App) などのメール クライアントでブロックするメッセージのヘッダーを取得します。

2. [メッセージ ヘッダー アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)を使用するか、または手動で、X-Forefront-Antispam-Report ヘッダー内の CIP タグの後に続く IP アドレスを検索します。

3. 「[接続フィルター ポリシーを構成する](configure-the-connection-filter-policy.md)」の「EAC を使用して既定の接続フィルター ポリシーを編集する」に示された手順に従って、その IP アドレスを IP 禁止一覧に追加します。

### <a name="block-bulk-mail-with-mail-flow-rules-transport-rules-or-the-spam-filter"></a>メール フロー ルール (トランスポート ルール) またはスパム フィルターでバルク メールをブロックする

スパムが主にニュースレターやプロモーションなどのバルク メールの場合、[メール フロー ルールを使用してバルク メールのフィルター処理を構成する](use-transport-rules-to-configure-bulk-email-filtering.md)か、スパム フィルターの[高度なスパム フィルター (ASF) の設定](advanced-spam-filtering-asf-options.md)で**バルク メール**設定をオンにすると、Office 365 でスパム フィルターをカスタマイズすることができます。Exchange 管理センターで、**[保護]** \> **[コンテンツ フィルター]** をクリックし、調整するフィルター ポリシーをダブルクリックして作業を開始します。下記に示すとおり、**[スパムおよびバルク メール操作]** をクリックして設定を調整します。

![Exchange Online でバルク メール フィルターを設定する](../../media/a45095c2-269d-45b8-a76c-999b5e78da68.png)

### <a name="block-email-spam-using-spam-filter-block-lists"></a>スパム フィルター禁止一覧を使用して迷惑メールをブロックする

[Office 365 でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)して、スパム フィルターの送信者禁止一覧に送信者アドレスを追加するか、ドメイン禁止一覧にドメインを追加します。スパム フィルター禁止一覧にある送信者やドメインからのメールはスパムとしてマークされます。

## <a name="email-users-can-also-help-ensure-that-false-negative-and-email-spam-is-blocked-with-spam-filter"></a>メール ユーザーは、スパム フィルターを使用して、確実に検出漏れや迷惑メールをブロックすることもできます。

これは、スパム対策で、[Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) または [Outlook on the web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) のスパム送信者一覧にスパム送信者アドレスを追加するようユーザーに指示した場合に、検出漏れや迷惑メールを防止するのに役立ちます。Outlook on the web では、ここで示すとおり、**[設定]** \> **[オプション]** \> **[ブロックまたは許可]** をクリックし、**[ブロックする差出人]** 一覧にアドレスを追加します。

![Outlook on the web で送信者をブロックする](../../media/fdf51381-2527-4819-ac2a-5dff84d2a36d.png)

> [!NOTE]
> 差出人セーフ リストの詳細については、「[Office 365 で信頼できる差出人リストを作成する](create-safe-sender-lists-in-office-365.md)」を参照してください。

## <a name="eop-only-customers-set-up-directory-synchronization"></a>EOP のみのユーザー: ディレクトリ同期のセットアップ

ディレクトリ同期を使用してユーザー設定をサービスと同期させ、ブロックする差出人が考慮されるようにすると、検出漏れの迷惑メールを回避するのに役立ちます。詳細については、EOP のメール ユーザー管理で「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。

## <a name="eop-only-customers-who-are-not-using-directory-synchronization"></a>ディレクトリ同期を使用していない EOP のみのお客様

EOP サービスは、情報がサービスと共有されている場合、ユーザーの安全な差出人とブロックする差出人を尊重するように設計されています。Outlook を使用している EOP のお客様で、ユーザーを Office 365 に同期させるようにディレクトリ同期を構成していない場合でも、ブロックする差出人を使用してユーザーの受信トレイにメッセージが配信されないようにできます。ただし、次の状況ではいくつかの Exchange メール フロー ルールを設定する必要があります。

- メッセージが EOP による通常のスパム フィルター処理を経てローカルのオンプレミス Exchange サーバーに配信され、EOP が SCL 1 から 4 (非スパム) のスパム判定を割り当てた場合、ユーザーのローカルの受信拒否リストが EOP スパム フィルターの判定をオーバーライドし、メッセージは迷惑メール フォルダーに配信されます。

- Exchange メール フロー ルールによって、または IP アドレスやドメインが許可一覧に含まれていることで、EOP のメッセージに SCL -1 が割り当てられている場合、SCL はコネクタを使用してオンプレミス Exchange サーバーに伝達されます。この場合、ユーザーの受信拒否リストは適用されません。この動作を変更するには、SCL を 0 に設定するローカルのメール フロー ルールを作成します。これにより、Outlook はユーザーのローカルの受信拒否リストを適用します。

### <a name="to-set-up-a-mail-flow-rule-to-stop-messages-from-being-delivered-to-your-users-inbox-by-using-the-blocked-senders-list"></a>受信拒否リストを使用して、メッセージがユーザーの受信トレイに配信されないように、メール フロー ルールを設定するには

1. オンプレミス サーバーで Exchange 管理シェルを開きます。オンプレミスの Exchange 組織でシェルを開く方法については、「[Exchange 管理シェルを開く](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)」を参照してください。

2. SCL -1 とマークされたすべてのメッセージで SCL を更新するには、次のコマンドを実行してコンテンツでフィルタリングされたスパム メッセージを迷惑メール フォルダーにルーティングします。

   ```powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SCL:-1" -SetSCL 0
   ```

   SCL はオンプレミス Exchange サーバーでは 0 なので、非スパムはユーザーの受信トレイに配信されますが、ユーザーのローカルの受信拒否リストによって迷惑メール フォルダーに送信されことも可能です。EOP でスパム検疫を使用している場合も、ユーザーのセーフ リストに記載されている送信者がスパムとして識別され、検疫に送られる可能性があります。ただし、ローカルのメールボックスで迷惑メール フォルダーを使用している場合、この操作で、安全な送信者用の受信トレイへの配信が可能になります。

> [!WARNING]
> メール フロー ルールを使用して SCL 値を 0 (または -1 以外の値) に変更すると、すべての Outlook の迷惑メール オプションがメッセージに適用されます。これは、ブロック リストおよびセーフ リストが尊重されるようになることを意味しますが、ブロック リストやセーフ リストにアドレスが記載されていないメッセージは、クライアント側の迷惑メール フィルター処理によって迷惑メールとしてマークされる可能性があるということも意味します。Outlook にブロック リストとセーフ リストを処理させる必要があるものの、クライアント側の迷惑メール フィルターは使用したくない場合は、Outlook の迷惑メール オプションでオプションを「自動フィルター処理なし」に設定する必要があります。最新バージョンの Outlook では、「自動フィルター処理なし」が既定のオプションですが、クライアント側の迷惑メール フィルターがメッセージに適用されないようにするために、この設定になっていることを確認する必要があります。管理者は、「[Outlook: 迷惑メールの UI とフィルター処理機構を無効にするポリシー設定](https://support.microsoft.com/kb/2180568)」の手順に従って、Outlook の迷惑メール フィルター処理を無効にすることができます。

## <a name="see-also"></a>関連項目

[Microsoft 365 でのスパム対策保護](anti-spam-protection.md)

[セーフリストまたはその他の手法で誤検知の電子メールがスパムとしてマークされないようにする](prevent-email-from-being-marked-as-spam.md)
