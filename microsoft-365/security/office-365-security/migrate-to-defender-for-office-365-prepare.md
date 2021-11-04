---
title: 'Microsoft Defender に移行して、Office 365フェーズ 1: 準備する'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: migrationguides
description: サード パーティ製の保護サービスまたはデバイスから Microsoft Defender に移行して保護を行う場合のOffice 365手順。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6785e96829256ffe0763eb0f3e84059973d6379
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785800"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-1-prepare"></a>Microsoft Defender に移行して、Office 365 - フェーズ 1: 準備する

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

<br>

|![フェーズ 1: 準備します。](../../media/phase-diagrams/prepare.png) <br> フェーズ 1: 準備|[![フェーズ 2: 設定](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [フェーズ 2: 設定](migrate-to-defender-for-office-365-setup.md)|[![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [フェーズ 3: オンボード](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
|*お前はここにいる!*|||

フェーズ **1 へようこそ: Microsoft** Defender への移行の準備を **[Office 365!](migrate-to-defender-for-office-365.md#the-migration-process)** この移行フェーズには、次の手順が含まれます。 変更を加える前に、まず既存の保護サービスで設定をインベントリする必要があります。 それ以外の場合は、残りの手順を任意の順序で実行できます。

1. [既存の保護サービスで設定をインベントリする](#inventory-the-settings-at-your-existing-protection-service)
2. [既存の保護構成を確認Microsoft 365](#check-your-existing-protection-configuration-in-microsoft-365)
3. [メール ルーティングの構成を確認する](#check-your-mail-routing-configuration)
4. [メッセージを変更する機能をユーザーにMicrosoft 365](#move-features-that-modify-messages-into-microsoft-365)
5. [スパムと一括ユーザー エクスペリエンスの定義](#define-spam-and-bulk-user-experiences)
6. [優先度アカウントの特定と指定](#identify-and-designate-priority-accounts)

## <a name="inventory-the-settings-at-your-existing-protection-service"></a>既存の保護サービスで設定をインベントリする

既存の保護サービスからの設定、ルール、例外などの完全なインベントリは、サブスクリプションをキャンセルした後に情報にアクセスできない可能性が高いので、良いアイデアです。

**ただし、Defender ですべての既存のカスタマイズを自動的に再作成したり、任意に再作成したりしないのは非常にOffice 365。** 最適な場合は、不要になった設定、関連性のある設定、または機能する設定を導入できます。 さらに悪いことに、以前のカスタマイズの中には、実際に Defender でセキュリティ上の問題が発生Office 365。

Defender for Office 365のネイティブ機能と動作のテストと観察によって、最終的に必要な上書きと設定が決定されます。 既存の保護サービスから次のカテゴリに設定を分類すると便利な場合があります。

- **接続またはコンテンツ のフィルター** 処理 : Defender でこれらのカスタマイズのほとんどを必要としない可能性Office 365。
- **ビジネス ルーティング**: 再作成する必要があるカスタマイズの大部分は、このカテゴリに分類される可能性があります。 たとえば、これらの設定を Microsoft 365 メール フロー Exchange (トランスポート ルールとも呼ばれる)、コネクタ、およびスプーフィング インテリジェンスの例外として再作成できます。

古い設定を Microsoft 365 に盲目的に移動する代わりに、ユーザー メンバーシップの増加に伴うパイロット フェーズと、セキュリティに関する考慮事項と組織のビジネス ニーズのバランスに基づく監視ベースの調整を含むウォーターフォール アプローチをお勧めします。

## <a name="check-your-existing-protection-configuration-in-microsoft-365"></a>既存の保護構成を確認Microsoft 365

前に述べたように、サードパーティの保護サービスを使用している場合でも、Microsoft 365 に配信されるメールのすべての保護機能を完全にオフにすることはできません。 そのため、組織が少なくとも一部の電子Microsoft 365機能を構成するのも珍しいことではありません。 例:

- 過去には、サードパーティ製の保護サービスを使用してセキュリティ保護サービスを使用Microsoft 365。 現在無視されている一部の保護機能は、Microsoft 365使用して構成している可能性があります。 ただし、これらの設定は、「ダイヤルを回す」と有効になる Microsoft 365場合があります。
- Microsoft 365 保護には、既存の保護サービスを通じて誤検知 (悪いマークが付いた良いメール) または偽陰性 (悪いメールが許可されている) に対する宿泊施設がある場合があります。

既存の保護機能をMicrosoft 365、不要になった設定の削除または簡略化を検討してください。 何年も前に必要だったルールまたはポリシー設定は、組織を危険にさらし、保護に意図しないギャップを生み出す可能性があります。

## <a name="check-your-mail-routing-configuration"></a>メール ルーティングの構成を確認する

- 何らかの複雑なルーティング (たとえば、集中メール トランスポート[](/exchange/transport-options)) を使用している場合は、ルーティングを簡略化し、完全に文書化する必要があります。 外部ホップは、特Microsoft 365メッセージを受信した後、構成とトラブルシューティングを複雑にできます。

- 送信メール フローと中継メール フローは、この記事の範囲を外しています。 ただし、次の 1 つ以上の手順を実行する必要がある場合があります。
  - 電子メールの送信に使用するドメインのすべてが、適切な SPF レコードを持っている必要があります。 詳細については、「[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。
  - DKIM サインインをセットアップすることを強く推奨Microsoft 365。 詳細については [、「DKIM を使用して送信メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。
  - 送信コネクタから直接メールをルーティングしないMicrosoft 365、送信コネクタを削除または変更して、そのルーティングを変更する必要があります。

- このMicrosoft 365を使用して、オンプレミスの電子メール サーバーから電子メールを中継すると、それ自体が複雑なプロジェクトになる可能性があります。 簡単な例は、メッセージのほとんどを内部受信者に送信するアプリやデバイスの数が少ない場合で、大量のメールには使用されません。 詳細 [については、このガイド](/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365) を参照してください。 より広範な環境では、より慎重にする必要があります。 受信者がスパムと見なす可能性があるマーケティング 電子メールとメッセージは許可されません。

- DMARC Office 365を集計する機能を持つユーザー向け Defender を使用します。 Microsoft [Intelligent Security Association (MISA)](https://www.microsoft.com/misapartnercatalog)カタログにアクセスして、DMARC レポートを提供するサード パーティベンダーを表示Microsoft 365。

## <a name="move-features-that-modify-messages-into-microsoft-365"></a>メッセージを変更する機能をユーザーにMicrosoft 365

メッセージを変更するカスタマイズや機能を、任意の方法でユーザー設定にMicrosoft 365。 たとえば、既存の保護サービスは、外部送信者からのメッセージの件名またはメッセージ本文に外部タグを追加します。

既存の保護サービスでこの機能を無効にしない場合は、次のような負の結果が発生Microsoft 365。

- DKIM が壊れる。
- [スプーフィング](anti-spoofing-protection.md) インテリジェンスが正しく動作しません。
- 誤検知の数が多い (良いメールが正しいとマークされている) 可能性があります。

この機能を Microsoft 365するには、次のオプションがあります。

- 外部[Outlookの呼び出し機能と](https://techcommunity.microsoft.com/t5/exchange-team-blog/native-external-sender-callouts-on-email-in-outlook/ba-p/2250098)、最初の連絡先の安全[に関するヒントを提供します](set-up-anti-phishing-policies.md#first-contact-safety-tip)。
- メール フロー ルール (トランスポート ルールとも呼ばれる)。 詳細については、「組織全体の[メッセージ](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)免責事項、署名、フッター、またはヘッダー」を参照Exchange Online。

## <a name="account-for-any-active-phishing-simulations"></a>アクティブなフィッシング シミュレーションのアカウント

アクティブなサード パーティのフィッシング シミュレーションがある場合は、メッセージ、リンク、添付ファイルが Defender for Office 365 によってフィッシングとして識別されるのを防ぐ必要があります。 詳細については、「高度な配信ポリシーでサードパーティのフィッシング シミュレーションを構成 [する」を参照してください](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)。

## <a name="define-spam-and-bulk-user-experiences"></a>スパムと一括ユーザー エクスペリエンスの定義

- **検疫と迷惑メール フォルダー** への配信: 悪意のある、確実に危険なメッセージに対する自然で推奨される応答は、メッセージを検疫する方法です。 ただし、迷惑メールやバルク メール (グレー メールとも呼ばれる) などの有害なメッセージをユーザーに処理する方法は *何ですか*。 これらの種類のメッセージは、ユーザーの迷惑メール フォルダーに配信する必要がありますか?

  標準のセキュリティ設定では、通常、これらのリスクの低い種類のメッセージを迷惑メール フォルダーに配信します。 この動作は、ユーザーが迷惑メール フォルダーで不足しているメッセージを確認し、それらのメッセージ自体を救出できる、多くの消費者向け電子メール サービスに似ています。 または、ユーザーが意図的にニュースレターやマーケティング メールにサインアップした場合は、自分のメールボックスの送信者を購読解除またはブロックすることができます。

  ただし、多くのエンタープライズ ユーザーは、迷惑メール フォルダー内のメールが少ない (その場合) 使用されます。 代わりに、これらのエンタープライズ ユーザーは、不足しているメッセージの検疫をチェックするために使用されます。 検疫では、検疫通知、通知頻度、およびメッセージの表示と解放に必要なアクセス許可の問題が導入されています。

  - ドメイン キー識別メール (DKIM) が壊れる。
  - [スプーフィング](anti-spoofing-protection.md) インテリジェンスが正しく動作しません。
  - 誤検知の数が多い (良いメールが正しいとマークされている) 可能性があります。

  最終的には、検疫への配信を支持して迷惑メール フォルダーへの電子メールの配信を防止する場合は、この決定が必要です。 ただし、1 つのことは確かです。Office 365 の Defender でのエクスペリエンスがユーザーの慣例とは異なる場合は、ユーザーに通知し、基本的なトレーニングを提供する必要があります。 パイロットからの学習を組み込み、ユーザーが電子メール配信の新しい動作に備えて準備されている必要があります。

- **望ましくないバルク メールと望** ましくないバルク メール : 多くの保護システムにより、ユーザーは自分でバルク メールを許可またはブロックできます。 これらの設定は簡単には移行できないのでMicrosoft 365で既存の構成を再作成するために、VIP とそのスタッフとの作業を検討Microsoft 365。

  今日、Microsoft 365一括メール (ニュースレターなど) は、メッセージ ソースに基づいて安全と見なされています。 これらの "安全な" ソースからのメールは、現在バルクとしてマークされていない (バルク 苦情レベルまたは BCL は 0 または 1) ので、これらのソースからのメールをグローバルにブロックすることは困難です。 ほとんどのユーザーにとって、ソリューションは、これらのバルク メッセージを個別に購読解除するか、送信者をブロックするためにOutlookを使用します。 ただし、一部のユーザーは、バルク メッセージ自体をブロックまたはブロック解除する必要があります。

  バルク メールをフィルター処理するメール フロー ルールは、VIP ユーザーがこれを自分で管理しない場合に役立ちます。 詳細については、「メール フロー ルールを [使用してバルク メールをフィルター処理する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-filter-bulk-mail)。

## <a name="identify-and-designate-priority-accounts"></a>優先度アカウントの特定と指定

この機能を利用できる場合は、優先度アカウントとユーザー タグを使用すると、重要なユーザーを特定し、Microsoft 365目立つユーザーを特定できます。 詳細については、「Microsoft [Defender の User tags for Office 365](user-tags.md)および優先度アカウントの管理と監視」[を参照してください](/microsoft-365/admin/setup/priority-accounts)。

## <a name="next-step"></a>次の手順

**おめでとう** ございます! Microsoft Defender への移行の **準備** フェーズを完了し [、Office 365!](migrate-to-defender-for-office-365.md#the-migration-process)

- [フェーズ [2: セットアップ] に進みます](migrate-to-defender-for-office-365-setup.md)。
