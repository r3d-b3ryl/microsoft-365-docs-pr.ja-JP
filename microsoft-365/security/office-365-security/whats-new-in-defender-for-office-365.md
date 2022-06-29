---
title: Microsoft Defender for Office 365 の新機能
description: 最新リリースのMicrosoft Defender for Office 365で利用できる新機能について説明します。
keywords: Microsoft Defender for Office 365、ga、一般公開、機能、利用可能、新規の新機能
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords: NOCSH
ms.author: tracyp
author: msfttracyp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 37819c0f5ea458a4f5ee25b3536e3688aabd1882
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66486909"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の新機能

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象:**

- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事では、Microsoft Defender for Office 365の最新リリースの新機能の一覧を示します。 現在プレビュー中の機能は **、(プレビュー)** と表示されます。

[このビデオ](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)を見て詳細をご確認ください。

他の Microsoft Defender セキュリティ製品の新機能の詳細については、次を参照してください。

- [Microsoft 365 Defender の新機能](../defender/whats-new.md)
- [Microsoft Defender for Endpoint の新機能](../defender-endpoint/whats-new-in-microsoft-defender-endpoint.md)
- [Microsoft Defender for Identityの新機能](/defender-for-identity/whats-new)
- [Microsoft Cloud App Securityの新機能](/cloud-app-security/release-notes)


## <a name="june-2022"></a>2022 年 6 月

- [スプーフィングでは、管理者の申請を使用できます](allow-block-email-spoof.md#use-admin-submission-in-microsoft-365-defender)。テナント許可/ブロック リストを使用して、許可されたスプーフィングされた送信者エントリを作成します。

- [権限借用では管理者申請を使用できます](allow-block-email-spoof.md#create-impersonated-sender-entries)。追加では、Microsoft 365 Defenderの [送信] ページを使用して偽装された送信者を許可します。

- [ユーザー申請から変換された管理者の申請を表示](admin-submission.md#convert-user-reported-messages-from-the-custom-mailbox-into-an-admin-submission)する: 分析のために Microsoft にメッセージを送信せずに、ユーザーが報告したメッセージを傍受するようにカスタム メールボックスを構成します。

- [ユーザーと管理者の提出に関連するアラートを表示](admin-submission.md#view-associated-alert-for-user-and-admin-email-submissions)する: フィッシング メッセージと管理者の電子メール送信が報告された各ユーザーに対応するアラートを表示します。 

- [構成可能な偽装保護のカスタム ユーザーとドメイン、およびプリセット ポリシー内のスコープの増加](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/configurable-impersonation-protection-and-scope-for-preset/ba-p/3294459):
  - (選択)事前設定された Strict/Standard ポリシーを組織全体に適用し、特定の受信者ユーザー、グループ、またはドメインを選択する手間を省き、組織のすべての受信者ユーザーをセキュリティで保護します。 
  - 事前設定された Strict/Standard ポリシー内でカスタム ユーザーとカスタム ドメインの偽装保護設定を構成し、偽装攻撃から対象ユーザーとターゲット ドメインを自動的に保護します。

- [office 365 のMicrosoft 365 Defenderでの検疫エクスペリエンスの簡略化 (パート 2):](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience-part-two/ba-p/3354687) 検疫エクスペリエンスをさらに使いやすくするための追加機能を強調表示します。

## <a name="april-2022"></a>2022 年 4 月

- [Microsoft 365 Defender Advanced Hunting の URLClickEvents テーブルの概要](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/introducing-the-urlclickevents-table-in-advanced-hunting-with/ba-p/3295096): Microsoft Defender for Office 365を使用した高度なハンティングの UrlClickEvents テーブルの概要。
- [手動による電子メール修復の機能強化](/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365): 新しいアクションに焦点を当てた調査を使用して、Microsoft Defender for Office 365で実行された手動の電子メール消去アクションを、Microsoft 365 Defender (M365D) 統合アクション センターに取り込みます。
 
## <a name="march-2022"></a>2022 年 3 月

- [Microsoft Defender for Office 365での提出エクスペリエンスの効率化](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/streamlining-the-submissions-experience-in-microsoft-defender/ba-p/3152080): 新しい統合された合理化された提出プロセスを紹介し、エクスペリエンスをシンプルにします。

## <a name="january-2022"></a>2022 年 1 月

- [Microsoft Defender for Office 365のハンティングと調査のエクスペリエンスの更新](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/updated-hunting-and-investigation-experiences-for-microsoft/ba-p/3002015): Defender for Office 365のエクスペリエンスに関する電子メール の概要パネルと、脅威エクスプローラーとリアルタイム検出のエクスペリエンス更新プログラムを紹介します。

## <a name="october-2021"></a>2021 年 10 月

- [高度な配信 DKIM の強化](configure-advanced-delivery.md): サード パーティのフィッシング シミュレーション構成の一環として、DKIM ドメイン エントリのサポートが追加されました。
- [既定でセキュリティ保護](secure-by-default.md): Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) の場合は、既定でセキュリティで保護されています。

## <a name="september-2021"></a>2021 年 9 月

- [Defender for Office 365でのレポート エクスペリエンスの向上](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/improving-the-reporting-experience-in-microsoft-defender-for/ba-p/2760898)
- [検疫ポリシー](quarantine-policies.md): 管理者は、検疫されたメッセージへの受信者アクセスの詳細な制御を構成し、エンドユーザーのスパム通知をカスタマイズできます。
  - [管理者エクスペリエンスのビデオ](https://youtu.be/vnar4HowfpY)
  - [エンド ユーザー エクスペリエンスのビデオ](https://youtu.be/s-vozLO43rI)
  - 検疫エクスペリエンスに関するその他の新機能については、このブログ記事「 [検疫エクスペリエンスの簡略化](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388)」で説明しています。
- ポータルのリダイレクトは既定で開始され、セキュリティ & コンプライアンスから Microsoft 365 Defender <https://security.microsoft.com>にユーザーがリダイレクトされます。 詳細については、「Office 365 [セキュリティ & コンプライアンス センターからMicrosoft 365 Defenderへのアカウントのリダイレクト」を](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)参照してください。

## <a name="august-2021"></a>2021 年 8 月

- [報告されたメッセージの管理レビュー](admin-review-reported-message.md): 管理者は、報告されたメッセージを確認した後、テンプレート化されたメッセージをエンド ユーザーに返送できるようになりました。 テンプレートは、組織に合わせてカスタマイズでき、管理者の評決にも基づいてカスタマイズできます。
- [テナント許可/ブロック リストに許可を](manage-tenant-allows.md)追加する: ブロックされたメッセージが管理者申請プロセスの一部として送信された場合に、許可エントリをテナント許可/ブロック リストに追加できるようになりました。 ブロックの性質に応じて、送信された URL、ファイル、送信者の許可がテナント許可/ブロック リストに追加されます。 ほとんどの場合、許可が追加され、システムに時間が与え、保証されていれば自然に許可されます。 場合によっては、Microsoft によって許可が管理されます。

## <a name="july-2021"></a>2021 年 7 月

- [自動調査の電子メール分析の機能強化](email-analysis-investigations.md)
- [高度な配信](configure-advanced-delivery.md): サード パーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージをセキュリティ操作メールボックスに配信するための新しい機能を導入しました。
- [Microsoft Teams の安全なリンク](safe-links.md#safe-links-settings-for-microsoft-teams)
- 次のシナリオの新しいアラート ポリシー: 侵害されたメールボックス、フォームフィッシング、オーバーライドが原因で配信された悪意のあるメール、ZAP の丸め
  - 疑わしいメール転送アクティビティ
  - フォームの共有と応答の収集について制限されたユーザー
  - フィッシング詐欺の可能性が原因でブロックされたフォーム
  - フラグが設定され、フィッシングが確認されたフォーム
  - [ZAP の新しいアラート ポリシー](../../compliance/new-defender-alert-policies.md)
- Microsoft Defender for Office 365アラートがMicrosoft 365 Defenderに統合されるようになりました - [統合アラート キューと統合アラート キュー Microsoft 365 Defender](../defender/investigate-alerts.md)
- [ユーザー タグ](user-tags.md)は、Microsoft Defender for Office 365アラート エクスペリエンス (Office 365 Security & Compliance のアラート キューと詳細、ユーザー タグへのカスタム アラート ポリシーのスコープ設定など) に統合され、対象のアラート ポリシーが作成されるようになりました。
  - タグは、Microsoft 365 Defender ポータルの統合アラート キューでも使用できます (プラン 2 Microsoft Defender for Office 365)

## <a name="june-2021"></a>2021 年 6 月

- フィッシング対策ポリシー内の新しい最初の連絡先の安全ヒント設定。 この安全に関するヒントは、受信者が最初に送信者から電子メールを受信したとき、または送信者から電子メールを受信しない場合に表示されます。 この設定とその構成方法の詳細については、次の記事を参照してください。
  - [最初の連絡先の安全に関するヒント](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)
  - [詳細については、「Microsoft Defender for Office 365 のフィッシング対策ポリシーを構成する」を参照してください。](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>2021 年 4 月/5 月

- [電子メール エンティティ ページ](mdo-email-entity-page.md): 脅威、認証と検出、起爆の詳細、およびまったく新しいメール プレビュー エクスペリエンスに関する情報を含む、電子メールの 360 度の統合ビュー。
- [Office 365 Management API](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events): EmailEvents (RecordType 28) に更新して、配信アクション、元の配信場所と最新の配信場所、および更新された検出の詳細を追加します。
- [Defender for Office 365用の Threat Analytics](/microsoft-365/security/defender/threat-analytics): アクティブな脅威アクター、一般的な手法、攻撃面を表示し、進行中のキャンペーンに関する Microsoft の研究者からの広範なレポートを表示します。

## <a name="februarymarch-2021"></a>2021 年 2 月/3 月

- [ハンティング エクスペリエンス](threat-explorer.md)でのアラート ID の統合 (アラート ID とAlert-Explorer ナビゲーションを使用した検索)
- [ハンティング エクスペリエンス](threat-explorer.md)でレコードのエクスポートの制限を 9990 から 200,000 に増やす
- エクスプローラー (およびリアルタイム検出) のデータリテンション期間と試用版テナントの検索制限を 7 日 (以前の制限) から 30 日間の[ハンティング エクスペリエンス](threat-explorer.md)に拡張する
- エクスプローラー内の **偽装されたドメイン** と **偽装されたユーザー** (およびリアルタイム検出) と呼ばれる新しいハンティング ピボット。保護されたユーザーまたはドメインに対する偽装攻撃を検索します。 詳細については、詳細を参照 [してください](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。 (Microsoft Defender for Office 365 プラン 1 またはプラン 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 プラン 1 およびプラン 2

Microsoft Defender for Office 365が 2 つのプランで利用できることをご存じですか? [各プランに含まれる内容の詳細については、こちらを参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="see-also"></a>関連項目

- [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)
- [Microsoft Defender for Office 365 サービスの説明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
