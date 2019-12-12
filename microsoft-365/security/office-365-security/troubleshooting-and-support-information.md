---
title: トラブルシューティングとサポート情報
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: このトピックでは、エンドユーザーと管理者向けのトラブルシューティング手順と、支援を得るためのテクニカル サポートへの問合わせ方法について説明します。
ms.openlocfilehash: a6a4b94db3e34442d326942641b10db15d104d71
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971625"
---
# <a name="troubleshooting-and-support-information"></a>トラブルシューティングとサポート情報

このトピックでは、エンドユーザーと管理者向けのトラブルシューティング手順と、支援を得るためのテクニカル サポートへの問合わせ方法について説明します。

## <a name="troubleshooting-for-users"></a>ユーザー向けのトラブルシューティング

迷惑メール報告アドインを追加した後、Microsoft Outlook で問題が発生することがあります。 発生する可能性のある問題とそれらの問題を解決するためのヒントを以下に示します。

- **[迷惑メールの報告]** をクリックしても何も起こらない

- 電子メール メッセージを選択した後に Outlook が応答しなくなった

- "配信不能" と返され、報告された迷惑メールを配信できない

この問題を解決するには、次の手順を実行します。

1. Outlook を閉じて、再起動します。

2. テスト メッセージを作成して、送信できることを確認します。これを実行するには、テスト メッセージを自分が管理する別の電子メール アカウントに送信し、電子メール メッセージが受信されることを確認します。

問題が解決しない場合は、管理者に問い合わせてください。

> [!TIP]
> また [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) 宛てにレポートを送信し、Microsoft に直接スパム メッセージを報告することもできます。さらに、誤検知のメッセージについては [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com) の電子メール アドレスに報告できます。詳細については、「 [スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。

## <a name="troubleshooting-for-administrators"></a>管理者向けのトラブルシューティング

管理者は、Outlook 用迷惑メール報告アドインを使用しているユーザーに問題が発生することがあります。 以下に、発生する可能性のある問題を解決するためのヒントを示します。

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>問題: ユーザーにシステム管理者に問い合わせるよう要求するエラーメッセージが継続的に表示される

1. 次のレジストリ キーの値を "Verbose" に設定します。

   - **32 ビットオペレーティングシステムにインストールされ32た Outlook**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32 ビットオペレーティングシステムにインストールされ64た Outlook**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **64 ビット Outlook (常に64ビットオペレーティングシステムにインストールされます)**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Outlook を再起動し、エラーメッセージが表示された場合にユーザーに報告するように依頼します。

3. 次の場所にあるログ情報を収集します。

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Exchange Online Protection テクニカル サポートに問い合わせ、ログ情報を提供します。

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>問題: ユーザーがメールを迷惑メールとして送信したときに、確認メッセージを表示しないように選択した

1. 次のレジストリキーの値を "True" に`HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`設定します。

2. Outlook を再起動します。

## <a name="support-information"></a>サポート情報

アドインのインストール、構成、またはアンインストールに関してサポートが必要な場合は、Microsoft 365 管理センターのサポートページにある [新しいサービスリクエスト] リンクを使用してテクニカルサポートにお問い合わせください。 電話およびセルフサポートオプション経由でのサービス要求の提出などのその他のオプションについては、「 [Help and support FOR EOP](help-and-support-for-eop.md)」を参照してください。

## <a name="for-more-information"></a>詳細情報

[レポート メッセージ アドインを有効にする](enable-the-report-message-add-in.md)

[迷惑メール メッセージを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)
