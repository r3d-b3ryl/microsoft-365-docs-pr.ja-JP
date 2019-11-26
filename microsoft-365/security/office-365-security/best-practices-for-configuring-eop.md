---
title: EOP および Office 365 ATP を構成するためのベストプラクティス
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。
ms.openlocfilehash: ccc312d6e3e9954ea38b10ebe9b4c8877a85b925
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257292"
---
# <a name="best-practices-for-configuring-eop"></a>EOP を設定するための最良の実施

Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。 このトピックでは、セットアップ プロセスが既に完了したことを前提としています。 まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。

## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。

## <a name="synchronize-recipients"></a>受信者の同期

組織でオンプレミスの Active Directory 環境に既存のユーザーアカウントがある場合は、それらのアカウントをクラウド内の Azure Active Directory と同期することができます。 ディレクトリ同期の使用をお勧めします。 ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。

## <a name="recommended-settings"></a>推奨設定

セキュリティ管理者は、自分の環境のニーズを satistfy するセキュリティ設定をカスタマイズできます。 原則として、EOP と Office 365 ATP には、標準と Strict の2つのセキュリティレベルがあります。 これらの設定は、 [EOP および Office 365 ATP security の推奨設定](recommended-settings-for-eop-and-office365-atp.md)に記載されています。 

### <a name="miscellaneousnon-policy-settings"></a>その他/ポリシー外の設定

これらの設定は、セキュリティポリシーの範囲外にある幅広い機能をカバーしています。

セキュリティ機能の名前|標準|Strict|コメント|
|---------|---------|---------|---------|
|[スプーフィングを防止するために Office 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|はい|はい||
|[DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)|はい|はい||
|[DMARC を使用して Office 365 で電子メールを検証する](use-dmarc-to-validate-email.md)|はい|はい|Action = [標準] の場合は [検疫] を、厳密には action = reject を使用します。|
|レポートメッセージのアドオンを展開して、疑わしいメールのエンドユーザーのレポートを向上させる|はい|はい||
|マルウェアおよびスパムレポートをスケジュールする|はい|はい||
|外部ドメインへの自動転送を許可または監視しない|はい|はい||
|統合監査を有効にする必要があります。|はい|はい||
|メールボックスへの IMAP 接続|無効|無効||
|メールボックスへの POP 接続|無効|無効||
|メールボックスへの SMTP 認証済み送信|無効|無効||
|メールボックスへの EWS 接続|無効|無効||
|PowerShell 接続|無効|無効||
|スプーフィングインテリジェンスを使用して、可能な場合には送信者をホワイトリストする|はい|はい||
|ディレクトリベースのエッジブロック (DBEB)|有効|有効|ドメインの種類 = 権限あり|
|[すべての管理者アカウントに対して多要素認証をセットアップする](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|有効|有効||

## <a name="troubleshooting"></a>トラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向をトラブルシューティングします。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 メッセージ トレース ツールの詳細については、「[Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)」を参照してください。

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>誤検知と誤検知を Microsoft に報告する

管理者は、管理者の送信ポータルを使用して、誤検知 (スパム) と誤検知 (非スパム) を Microsoft に送信する必要があります。 メール、ファイル、および Url を送信すると、管理者はエンドユーザーにメッセージを配信した理由を特定することができます。 詳細については、「問題の疑いがある[スパム、フィッシング、url、およびファイルを office 365 スキャン用に Microsoft に提出する方法](admin-submission.md)」を参照してください。

エンドユーザーは、指定された verdicts に同意しない場合に、偽陽性 (スパム) と誤検知 (非スパム) を Microsoft に直接報告して分析することもできます。 詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。


## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネスニーズに合わせてメールフロールールまたはカスタムフィルターを作成します。

新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。

新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。

組織にオンプレミスの Exchange と Office 365 の両方が含まれるハイブリッド環境では、メールフロールールで使用する条件を考慮します。 ルールを組織全体に適用する場合は、オンプレミスの Exchange と Office 365 の両方で使用できる条件を必ず使用してください。 両方の環境で使用可能な条件はほとんどありませんが、1つの環境またはその他の環境でのみ使用可能なものがいくつかあります。 詳細について[は、「メールフロールール (トランスポートルール) (Exchange Online)」を](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)参照してください。


