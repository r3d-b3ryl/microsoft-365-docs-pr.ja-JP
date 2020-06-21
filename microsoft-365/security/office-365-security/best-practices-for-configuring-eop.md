---
title: EOP を構成するためのベスト プラクティス
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Exchange Online Protection (EOP) のベストプラクティス推奨事項に従って、成功を設定し、一般的な構成エラーを回避します。
ms.openlocfilehash: e5e87883e9c8aad21552ebf306a9716f14532884
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739088"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>スタンドアロン EOP を構成するためのベストプラクティス

Exchange Online Protection (EOP) のベストプラクティス推奨事項に従って、成功を設定し、一般的な構成エラーを回避します。 このトピックでは、セットアップ プロセスが既に完了したことを前提としています。 まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。

## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。

## <a name="synchronize-recipients"></a>受信者の同期

組織でオンプレミスの Active Directory 環境に既存のユーザーアカウントがある場合は、それらのアカウントをクラウド内の Azure Active Directory と同期することができます。 ディレクトリ同期の使用をお勧めします。 ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。

## <a name="recommended-settings"></a>推奨設定

セキュリティ管理者は、組織のニーズを満たすようにセキュリティ設定をカスタマイズすることができます。 原則として、EOP と Office 365 ATP には、標準と Strict の2つのセキュリティレベルがあります。 これらの設定は、 [EOP および Office 365 ATP security の推奨設定](recommended-settings-for-eop-and-office365-atp.md)に記載されています。

### <a name="miscellaneousnon-policy-settings"></a>その他/ポリシー外の設定

これらの設定は、セキュリティポリシーの範囲外にある幅広い機能をカバーしています。

|||||
|---|---|---|---|
|**セキュリティ機能の名前**|**Standard**|**Strict**|**Comment**|
|[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|はい|はい||
|[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)|はい|はい||
|[DMARC を使用して Office 365 で電子メールを検証する](use-dmarc-to-validate-email.md)|はい|はい|を `action=quarantine` 標準として使用し、Strict に対して使用し `action=reject` ます。|
|[レポートメッセージアドイン](enable-the-report-message-add-in.md)を展開して、不審な電子メールのエンドユーザーのレポートを向上させる|はい|はい||
|マルウェアおよびスパムレポートをスケジュールする|はい|はい||
|外部ドメインへの自動転送を許可または監視しない|はい|はい||
|統合監査を有効にする必要があります。|はい|はい||
|[メールボックスへの IMAP 接続](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|[メールボックスへの POP 接続](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|無効|無効||
|認証済みの SMTP 送信|無効|無効|POP3 および IMAP4 クライアントが電子メールを送信するには、認証済みのクライアント SMTP 送信 (クライアント SMTP 発信または SMTP 認証とも呼ばれます) が必要です。|
|メールボックスへの EWS 接続|無効|無効||
|[PowerShell 接続](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|無効|無効|メールボックスユーザーまたはメールユーザー ([取得ユーザー](https://docs.microsoft.com/powershell/module/exchange/get-user)のコマンドレットによって返されるユーザーオブジェクト) に対して使用できます。|
|[スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)を使用して、許可リストに送信者を追加する|はい|はい||
|[ディレクトリベースのエッジブロック (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|有効|有効|ドメインの種類 = 権限あり|
|[すべての管理者アカウントに対して多要素認証をセットアップする](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|有効|有効||
|

## <a name="troubleshooting"></a>トラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向をトラブルシューティングします。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 メッセージ追跡ツールの詳細について[は、「Security & コンプライアンスセンター」の「メッセージ追跡」](message-trace-scc.md)を参照してください。

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>誤検知と誤検知を Microsoft に報告する

すべてのユーザーのサービスでスパムフィルター処理を改善するために、誤検知 (不良としてマークされている良好な電子メール) と誤検知 (無効な電子メールが許可されている) を分析のために Microsoft に報告する必要があります。 詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネスニーズを満たすように、メールフロールール (トランスポートルールとも呼ばれる) またはカスタムフィルターを作成します。

When you deploy a new rule to production, select one of the test modes first to see the effect of the rule. Once you are satisfied that the rule is working in the manner intended, change the rule mode to **Enforce**.

新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。

組織にオンプレミスの Exchange と Exchange Online の両方が含まれるハイブリッド環境では、メールフロールールで使用する条件を考慮します。 ルールを組織全体に適用する場合は、オンプレミスの Exchange と Exchange Online の両方で使用できる条件を必ず使用してください。 両方の環境で使用可能な条件はほとんどありませんが、1つの環境またはその他の環境でのみ使用可能なものがいくつかあります。 詳細について[は、「メールフロールール (トランスポートルール) (Exchange Online)」を](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)参照してください。
