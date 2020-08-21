---
title: EOP を構成するためのベスト プラクティス
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: スタンドアロンで成功に向けた設定を行い、一般的な構成エラーを防止するために、スタンドアロン Exchange Online Protection (EOP) に推奨されるベスト プラクティス推奨に従ってください。
ms.openlocfilehash: eb8e4aff765fbc1ab13c603f32ca0af51f87a4ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827667"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>スタンドアロン EOP を構成するためのベスト プラクティス

スタンドアロンで成功に向けた設定を行い、一般的な構成エラーを防止するために、スタンドアロン Exchange Online Protection (EOP) に推奨されるベスト プラクティス推奨に従ってください。 このトピックでは、セットアップ プロセスが既に完了したことを前提としています。 まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。

## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。

## <a name="synchronize-recipients"></a>受信者の同期

オンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合、そのアカウント情報とクラウドの Azure Active Directory を同期できます。 ディレクトリ同期の使用をお勧めします。 ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。

## <a name="recommended-settings"></a>推奨設定

セキュリティ管理者は、組織のニーズに合ううううでセキュリティ設定をカスタマイズすることができます。 一般的なルールとして、EOP および Office 365 ATP には、Standard と Strict の 2 つのセキュリティ レベルが推奨されます。 これらの設定は [、EOP および組織の 365 ATP セキュリティの [Officeされる設定] にリストされています](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="miscellaneousnon-policy-settings"></a>その他/ポリシー以外の設定

これらの設定は、セキュリティ ポリシーの範囲外の多範囲の機能をカバーします。

****

|セキュリティ機能名|Standard|Strict|コメント|
|---|---|---|---|
|[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|はい|はい||
|[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)|はい|はい||
|[DMARC を使用して Office 365 で電子メールを検証する](use-dmarc-to-validate-email.md)|はい|はい|`action=quarantine`Standard および `action=reject` Strict の場合に使用します。|
|迷惑 [メールの迷惑メール](enable-the-report-message-add-in.md) 報告をエンド ユーザーに報告する、迷惑メール報告アドインを展開する|はい|はい||
|マルウェアレポートとスパム レポートをスケジュールする|はい|はい||
|外部ドメインへの自動転送を許可または監視する必要がある|はい|はい||
|統合監査を有効にする必要があります|はい|はい||
|[メールボックスへの IMAP 接続](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|[メールボックスへの POP 接続](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|認証された SMTP 送信|無効|無効|POP3 クライアントと IMAP4 クライアントが電子メールを送信するには、認証されたクライアントの SMTP 送信 (クライアントの SMTP 送信または SMTP AUTH とも呼ばれる) が必要です。|
|メールボックスへの EWS 接続|無効|無効||
|[PowerShell の接続](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|無効|無効|メールボックス ユーザーまたはメール ユーザーに使用できます [(Get-User コマンドレットによって返されるユーザー](https://docs.microsoft.com/powershell/module/exchange/get-user) オブジェクト)。|
|ス [プーフィング インテリジェンス](learn-about-spoof-intelligence.md) を使用して送信者を許可リストに追加する|はい|はい||
|[ディレクトリベースのエッジ ブロック (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|有効|有効|ドメインの種類 = 権限あり|
|[すべての管理者アカウントに多要素認証を設定する](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|有効|有効||
|

## <a name="troubleshooting"></a>トラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向のトラブルシューティングを行います。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 セキュリティ センターのメッセージ追跡で、メッセージ [追跡ツールの詳細&確認してください](message-trace-scc.md)。

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>誤検知と偽陽性を Microsoft に報告する

すべてのユーザーがサービスでスパム フィルター処理を改善するには、誤検知 (悪くマークされていないメール) と誤検知 (不適切なメール) を分析のために Microsoft に報告する必要があります。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネス ニーズに合わせてメール フロー ルール (トランスポート ルールとも呼ばれる) またはカスタム フィルターを作成します。

新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。

新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。

組織にオンプレミスの Exchange と Exchange Online の両方が含まれるハイブリッド環境では、メール フロー ルールで使用する条件を検討します。 ルールを組織全体に適用する場合は、オンプレミスの Exchange と Exchange Online の両方で使用可能な条件を使用してください。 ほとんどの条件は両方の環境で使用可能ですが、一方の環境でのみ使用可能な条件があります。 詳細については [、Exchange Online のメール フロー ルール (トランスポート ルール) をご覧ください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
