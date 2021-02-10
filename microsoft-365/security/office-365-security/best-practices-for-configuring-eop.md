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
description: 成功を収め、一般的な構成エラーを回避するために、スタンドアロンの Exchange Online Protection (EOP) に関する以下のベスト プラクティスの推奨事項に従ってください。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a38454ceaba7f95dff172335dc374530efca20a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165933"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>スタンドアロン EOP を構成するためのベスト プラクティス

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protection スタンドアロン](https://go.microsoft.com/fwlink/?linkid=2148611)

成功を収め、一般的な構成エラーを回避するために、スタンドアロンの Exchange Online Protection (EOP) に関する以下のベスト プラクティスの推奨事項に従ってください。 このトピックでは、セットアップ プロセスが既に完了したことを前提としています。 まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。

## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。

## <a name="synchronize-recipients"></a>受信者の同期

組織にオンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合は、それらのアカウントをクラウド内の Azure Active Directory に同期できます。 ディレクトリ同期の使用をお勧めします。 ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。

## <a name="recommended-settings"></a>推奨設定

セキュリティ管理者は、組織のニーズに合わせてセキュリティ設定をカスタマイズできます。 ただし、一般的には、EOP と Office 365 用の Microsoft Defender には Standard と Strict の 2 つのセキュリティ レベルがあります。 これらの設定は、365 セキュリティを強化する EOP と [Microsoft Defender のOfficeに記載されています](recommended-settings-for-eop-and-office365-atp.md)。

### <a name="miscellaneousnon-policy-settings"></a>その他/ポリシー以外の設定

これらの設定は、セキュリティ ポリシーの外部にある一部の機能に対応しています。

****

|セキュリティ機能名|標準|Strict|Comment|
|---|---|---|---|
|[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|はい|はい||
|[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)|はい|はい||
|[DMARC を使用して Office 365 で電子メールを検証する](use-dmarc-to-validate-email.md)|はい|はい|標準 `action=quarantine` と厳密に `action=reject` 使用します。|
|レポート メッセージ [アドインまたは](enable-the-report-message-add-in.md) Report [Phishing](enable-the-report-phish-add-in.md) アドインを展開して、不審な電子メールに関するエンド ユーザーの報告を改善する|はい|はい||
|マルウェアとスパムのレポートをスケジュールする|はい|はい||
|外部ドメインへの自動転送を禁止または監視する必要がある|はい|はい||
|統合監査を有効にする|はい|はい||
|[メールボックスへの IMAP 接続](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|[メールボックスへの POP 接続](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|認証済み SMTP 送信|無効|無効|POP3 および IMAP4 クライアントが電子メールを送信するには、認証済みクライアント SMTP 送信 (クライアント SMTP 送信または SMTP AUTH とも呼ばれる) が必要です。|
|メールボックスへの EWS 接続|無効|無効||
|[PowerShell 接続](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|無効|無効|メールボックス ユーザーまたはメール ユーザー [(Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) コマンドレットによって返されるユーザー オブジェクト) で使用できます。|
|ス [プーフィング インテリジェンスを](learn-about-spoof-intelligence.md) 使用して送信者を許可リストに追加する|はい|はい||
|[ディレクトリ ベースのエッジ ブロック (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|有効|有効|Domain Type = Authoritative|
|[すべての管理者アカウントに対して多要素認証を設定する](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|有効|有効||
|

## <a name="troubleshooting"></a>トラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向をトラブルシューティングします。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 メッセージ追跡ツールの詳細については、セキュリティ/コンプライアンス センターのメッセージ [追跡&覧ください](message-trace-scc.md)。

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>誤検知と検出検出を Microsoft に報告する

すべてのユーザーに対してサービスのスパム フィルター処理を改善するには、分析のために誤検知 (良いメールが悪いとマークされている) と偽陰性 (悪いメールが許可されている) を Microsoft に報告する必要があります。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネス ニーズに合わせてメール フロー ルール (トランスポート ルールとも呼ばれる) またはカスタム フィルターを作成します。

新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。

新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。

組織にオンプレミスの Exchange と Exchange Online の両方が含まれるハイブリッド環境では、メール フロー ルールで使用する条件を検討します。 ルールを組織全体に適用する場合は、オンプレミスの Exchange と Exchange Online の両方で使用可能な条件を使用してください。 ほとんどの条件は両方の環境で使用できます。一方の環境または他の環境でのみ使用可能な条件もあります。 詳細については [、Exchange Online のメール フロー ルール (トランスポート ルール) を参照してください](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。
