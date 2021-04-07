---
title: EOP を構成するためのベスト プラクティス
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 成功のために自分自身をセットアップし、一般的な構成エラーを回避するために、スタンドアロンの Exchange Online Protection (EOP) に関するベスト プラクティスの推奨事項に従ってください。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94586d409d6d8b53ba68c22b6b4f62d2b72266db
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599477"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>スタンドアロン EOP を構成するためのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](exchange-online-protection-overview.md)

成功のために自分自身をセットアップし、一般的な構成エラーを回避するために、スタンドアロンの Exchange Online Protection (EOP) に関するベスト プラクティスの推奨事項に従ってください。 このトピックでは、セットアップ プロセスが既に完了したことを前提としています。 まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。

## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。

## <a name="synchronize-recipients"></a>受信者の同期

組織にオンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合は、それらのアカウントをクラウドの Azure Active Directory に同期できます。 ディレクトリ同期の使用をお勧めします。 ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。

## <a name="recommended-settings"></a>推奨設定

セキュリティ管理者は、組織のニーズを満たしてセキュリティ設定をカスタマイズできます。 一般的なルールとして、EOP と Microsoft Defender の 2 つのセキュリティ レベル (Office 365) を推奨します。標準と厳密です。 これらの設定は、EOP および Microsoft Defender のセキュリティ [365 の推奨Office一覧に記載されています](recommended-settings-for-eop-and-office365.md)。

### <a name="miscellaneousnon-policy-settings"></a>その他/ポリシー以外の設定

これらの設定は、セキュリティ ポリシー外の機能の範囲をカバーします。

<br>

****

|セキュリティ機能名|標準|Strict|コメント|
|---|---|---|---|
|[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|はい|はい||
|[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)|はい|はい||
|[DMARC を使用して Office 365 で電子メールを検証する](use-dmarc-to-validate-email.md)|はい|はい|標準 `action=quarantine` と厳密に `action=reject` 使用します。|
|不審な[メールの](enable-the-report-message-add-in.md)エンド ユーザー レポート[](enable-the-report-phish-add-in.md)を改善するために、レポート メッセージ アドインまたはレポート フィッシング アドインを展開する|はい|はい||
|マルウェアとスパム レポートのスケジュール設定|はい|はい||
|外部ドメインへの自動転送は禁止または監視する必要があります|はい|はい||
|統合監査を有効にする必要があります|はい|はい||
|[メールボックスへの IMAP 接続](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|[メールボックスへの POP 接続](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|認証された SMTP 申請|無効|無効|電子メールを生成および送信する POP3 および IMAP4 クライアントおよびアプリケーションおよびデバイスには、認証されたクライアント SMTP 申請 (クライアント SMTP 申請または SMTP AUTH とも呼ばれる) が必要です。 <p> SMTP AUTH をグローバルまたは選択的に有効または無効にする手順については、「Exchange Online で認証されたクライアント SMTP 送信を有効または無効にする」 [を参照してください](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)。|
|メールボックスへの EWS 接続|無効|無効|Outlook では、空き時間情報、アウトオブオフィス設定、および予定表の共有に Exchange Web Services を使用します。 EWS をグローバルに無効にできない場合は、次のオプションがあります。 <ul><li>クライアント [がモダン認証](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) (モダン認証) をサポートしている場合は、認証ポリシーを使用して EWS による基本認証の使用を防止します。</li><li>クライアント [アクセス ルールを使用して](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 、EWS を特定のユーザーまたは送信元 IP アドレスに制限します。</li><li>特定のアプリケーションへの EWS アクセスをグローバルまたはユーザーごとに制御します。 手順については、「Exchange で [EWS へのアクセスを制御する」を参照してください](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)。</li></ul> <p> レポート[メッセージ アドインと](enable-the-report-message-add-in.md)レポート[](enable-the-report-phish-add-in.md)フィッシング アドインは、サポートされている環境で既定で REST を使用しますが、REST が使用できない場合は EWS に戻ります。 REST を使用するサポートされている環境は次のとおりです。<ul><li>Exchange Online</li><li>Exchange 2019 または Exchange 2016</li><li>Microsoft 365 サブスクリプションまたは 1 回購入 Outlook 2019 からの現在の Outlook for Windows。</li><li>Microsoft 365 サブスクリプションまたは 1 回購入 Outlook for Mac 2016 以降からの現在の Outlook for Mac。</li><li>iOS 版および Android 版 Outlook</li><li>Outlook on the web</li></ul>|
|[PowerShell 接続](/powershell/exchange/disable-access-to-exchange-online-powershell)|無効|無効|メールボックス ユーザーまたはメール ユーザー [(Get-User](/powershell/module/exchange/get-user) コマンドレットによって返されるユーザー オブジェクト) で使用できます。|
|ス [プーフィング インテリジェンスを](learn-about-spoof-intelligence.md) 使用して送信者を許可リストに追加する|はい|はい||
|[ディレクトリ ベースのエッジ ブロック (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|有効|有効|ドメインの種類 = 権限|
|[すべての管理者アカウントの多要素認証を設定する](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|有効|有効||
|

## <a name="troubleshooting"></a>トラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向のトラブルシューティングを行います。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 メッセージ トレース ツールの詳細については、「セキュリティ コンプライアンス センター」の [「Message trace」&参照してください](message-trace-scc.md)。

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>誤検知と誤検知を Microsoft に報告する

すべてのユーザーに対してサービスのスパム フィルター処理を改善するには、誤検知 (悪いマークが付いた良い電子メール) と誤検知 (悪いメールが許可されている) を分析のために Microsoft に報告する必要があります。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネス ニーズを満たすメール フロー ルール (トランスポート ルールとも呼ばれる) またはカスタム フィルターを作成します。

新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。

新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。

組織にオンプレミスの Exchange と Exchange Online の両方が含まれるハイブリッド環境では、メール フロー ルールで使用する条件を検討します。 ルールを組織全体に適用する場合は、オンプレミスの Exchange と Exchange Online の両方で使用できる条件を必ず使用してください。 ほとんどの条件は両方の環境で使用できますが、一方の環境または他の環境でのみ使用できる条件がいくつか用意されています。 詳細については [、「Exchange Online のメール フロー ルール (トランスポート ルール)」を参照してください](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。