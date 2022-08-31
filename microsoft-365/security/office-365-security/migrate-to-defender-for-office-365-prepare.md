---
title: 'Microsoft Defender for Office 365 フェーズ 1 への移行: 準備'
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
- m365solution-mdo-migration
- highpri
ms.custom: migrationguides
description: サード パーティの保護サービスまたはデバイスからMicrosoft Defender for Office 365保護に移行するための前提条件の手順。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c772067d0c4ec14e20136f60b0c462f15f5c1e5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482166"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-1-prepare"></a>Microsoft Defender for Office 365への移行 - フェーズ 1: 準備

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

<br>

|![フェーズ 1: 準備します。](../../media/phase-diagrams/prepare.png) <br> フェーズ 1: 準備|[![フェーズ 2: 設定](../../media/phase-diagrams/setup.png#lightbox)](migrate-to-defender-for-office-365-setup.md) <br> [フェーズ 2: 設定](migrate-to-defender-for-office-365-setup.md)|[![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png#lightbox)](migrate-to-defender-for-office-365-onboard.md) <br> [フェーズ 3: オンボード](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
|*お客様はここにいます。*|||

**フェーズ 1 へようこそ:****[Microsoft Defender for Office 365への移行](migrate-to-defender-for-office-365.md#the-migration-process)** の準備を行います。 この移行フェーズには、次の手順が含まれます。 変更を行う前に、まず既存の保護サービスで設定をインベントリする必要があります。 それ以外の場合は、残りの手順を任意の順序で実行できます。

1. [既存の保護サービスで設定をインベントリする](#inventory-the-settings-at-your-existing-protection-service)
2. [Microsoft 365 で既存の保護構成を確認する](#check-your-existing-protection-configuration-in-microsoft-365)
3. [メール ルーティングの構成を確認する](#check-your-mail-routing-configuration)
4. [メッセージを変更する機能を Microsoft 365 に移動する](#move-features-that-modify-messages-into-microsoft-365)
5. [スパムと一括ユーザー エクスペリエンスを定義する](#define-spam-and-bulk-user-experiences)
6. [優先度アカウントを特定して指定する](#identify-and-designate-priority-accounts)

## <a name="inventory-the-settings-at-your-existing-protection-service"></a>既存の保護サービスで設定をインベントリする

サブスクリプションを取り消した後は情報にアクセスできない可能性があるため、既存の保護サービスからの設定、ルール、例外などの完全なインベントリをお勧めします。

**ただし、Defender for Office 365では、既存のすべてのカスタマイズを自動的または任意に再作成しないことが非常に重要です。** 必要な設定、関連する設定、または機能がなくなった設定を導入することをお勧めします。 さらに悪いことに、以前のカスタマイズの中には、実際にDefender for Office 365でセキュリティの問題が発生する可能性があります。

Defender for Office 365のネイティブ機能と動作のテストと観察によって、最終的に必要なオーバーライドと設定が決定されます。 既存の保護サービスの設定を次のカテゴリに分類すると便利な場合があります。

- **接続またはコンテンツのフィルター処理**: Defender for Office 365では、これらのカスタマイズのほとんどが必要ない可能性があります。
- **ビジネス ルーティング**: 再作成する必要があるカスタマイズの大半は、このカテゴリに分類される可能性があります。 たとえば、Microsoft 365 でこれらの設定を Exchange メール フロー ルール (トランスポート ルールとも呼ばれます)、コネクタ、およびスプーフィング インテリジェンスの例外として再作成できます。

古い設定を Microsoft 365 に盲目的に移行する代わりに、ユーザー メンバーシップが増え続けるパイロット フェーズと、セキュリティに関する考慮事項と組織のビジネス ニーズのバランスに基づく観察ベースのチューニングを伴うウォーターフォール アプローチをお勧めします。

## <a name="check-your-existing-protection-configuration-in-microsoft-365"></a>Microsoft 365 で既存の保護構成を確認する

前述のように、サードパーティの保護サービスを使用している場合でも、Microsoft 365 に配信されるメールのすべての保護機能を完全にオフにすることは不可能です。 そのため、Microsoft 365 組織で少なくとも一部の電子メール保護機能が構成されているのは珍しいことではありません。 以下に例を示します。

- 以前は、Microsoft 365 でサード パーティの保護サービスを使用していなかった。 Microsoft 365 で、現在無視されている保護機能を使用して構成した可能性があります。 ただし、Microsoft 365 で保護機能を有効にするために"ダイヤルを回す" と、これらの設定が有効になる場合があります。
- Microsoft 365 Protection には、既存の保護サービスを通じて誤検知 (不適切とマークされた良いメール) または偽陰性 (不正なメールが許可されている) の宿泊施設が含まれている場合があります。

Microsoft 365 の既存の保護機能を確認し、不要になった設定を削除または簡略化することを検討してください。 数年前に必要だったルールまたはポリシーの設定により、組織が危険にさらされ、保護に意図しないギャップが生じる可能性があります。

## <a name="check-your-mail-routing-configuration"></a>メール ルーティングの構成を確認する

- 任意の種類の複雑なルーティング ( [一元化されたメール トランスポート](/exchange/transport-options)など) を使用している場合は、ルーティングを簡略化し、完全に文書化することを検討する必要があります。 外部ホップ (特に Microsoft 365 が既にメッセージを受信した後) は、構成とトラブルシューティングを複雑にする可能性があります。

- 送信メール フローとリレー メール フローは、この記事の範囲外です。 ただし、次の手順のうち 1 つ以上を実行する必要がある場合があることに注意してください。
  - 電子メールの送信に使用するすべてのドメインに適切な SPF レコードがあることを確認します。 詳細については、「[SPF を設定して、スプーフィングを防止する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。
  - Microsoft 365 で DKIM 署名を設定することを強くお勧めします。 詳細については、「 [DKIM を使用して送信メールを検証する」を](use-dkim-to-validate-outbound-email.md)参照してください。
  - Microsoft 365 から直接メールをルーティングしない場合は、送信コネクタを削除または変更してそのルーティングを変更する必要があります。

- Microsoft 365 を使用してオンプレミスの電子メール サーバーからの電子メールを中継することは、それ自体が複雑なプロジェクトになる可能性があります。 簡単な例は、メッセージの大部分を内部受信者に送信し、大量の宛名には使用しない少数のアプリまたはデバイスです。 詳細については [、このガイド](/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365) を参照してください。 より広範な環境は、より思慮深くする必要があります。 受信者によるスパムと見なされる可能性があるマーケティング電子メールとメッセージは許可されません。

- Defender for Office 365には、DMARC レポートを集計するための機能はありません。 [Microsoft Intelligent Security Association (MISA) カタログ](https://www.microsoft.com/misapartnercatalog)にアクセスして、Microsoft 365 の DMARC レポートを提供するサード パーティベンダーを表示します。

## <a name="move-features-that-modify-messages-into-microsoft-365"></a>メッセージを変更する機能を Microsoft 365 に移動する

任意の方法でメッセージを変更するカスタマイズや機能を Microsoft 365 に転送する必要があります。 たとえば、既存の保護サービスは、 **外部** 送信者からのメッセージの件名またはメッセージ本文に外部タグを追加します。 リンク 折り返し機能を使用すると、一部のメッセージに問題が発生します。 このような機能を現在使用している場合は、問題を最小限に抑えるための代替手段として、セーフ リンクのロールアウトに優先順位を付ける必要があります。

既存の保護サービスでメッセージ変更機能を無効にしない場合、Microsoft 365 では次の負の結果が予想されます。

- DKIM は中断します。 すべての送信者が DKIM に依存しているわけではありませんが、その送信者は認証に失敗します。
- このガイドの後半の[スプーフィング インテリジェンス](anti-spoofing-protection.md)とチューニング手順は正しく機能しません。
- おそらく、誤検知の数が多くなります (不適切とマークされた良いメール)。

Microsoft 365 で外部送信者識別を再作成するには、次のオプションがあります。

- [Outlook 外部送信者の呼び出し機能](https://techcommunity.microsoft.com/t5/exchange-team-blog/native-external-sender-callouts-on-email-in-outlook/ba-p/2250098)と、[最初の連絡先の安全性に関するヒント](set-up-anti-phishing-policies.md#first-contact-safety-tip)。
- メール フロー ルール (トランスポート ルールとも呼ばれます)。 詳細については、[Exchange Onlineの組織全体のメッセージの免責事項、署名、フッター、またはヘッダーに関するページを参照](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)してください。

Microsoft は、近い将来、認証された受信チェーン (ARC) 標準をサポートするために業界と協力しています。 現在のメール ゲートウェイ プロバイダーでメッセージ変更機能を有効のままにする場合は、この標準をサポートする予定について連絡することをお勧めします。

## <a name="account-for-any-active-phishing-simulations"></a>アクティブなフィッシング シミュレーションのアカウント

アクティブなサード パーティのフィッシング シミュレーションがある場合は、メッセージ、リンク、添付ファイルがDefender for Office 365によってフィッシングとして識別されないようにする必要があります。 詳細については、「 [高度な配信ポリシーでサード パーティのフィッシング シミュレーションを構成する](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)」を参照してください。

## <a name="define-spam-and-bulk-user-experiences"></a>スパムと一括ユーザー エクスペリエンスを定義する

- **検疫と迷惑Emailフォルダーへの配信**: 悪意のある、間違いなく危険なメッセージに対する自然で推奨される応答は、メッセージを検疫することです。 ただし、スパムや一括メール ( *灰色のメール* とも呼ばれます) などの有害なメッセージをユーザーが処理する方法を説明します。 これらの種類のメッセージをユーザーの迷惑メール Email フォルダーに配信する必要がありますか?

  Standard セキュリティ設定では、通常、このようなリスクの低い種類のメッセージを迷惑メール Email フォルダーに配信します。 この動作は、多くのコンシューマー向けメール オファリングに似ています。ユーザーは迷惑メール Email フォルダーでメッセージが見つからないかどうかを確認でき、それらのメッセージを自分で救済できます。 または、ユーザーがニュースレターまたはマーケティング メールに意図的にサインアップした場合は、自分のメールボックスの送信者の登録を解除するかブロックするかを選択できます。

  ただし、多くのエンタープライズ ユーザーは、迷惑メール Email フォルダー内のほとんど (存在する場合) メールに使用されません。 代わりに、これらのエンタープライズ ユーザーは、不足しているメッセージの検疫をチェックするために使用されます。 検疫では、検疫通知、通知の頻度、およびメッセージを表示およびリリースするために必要なアクセス許可の問題が発生します。

  - ドメイン キーが識別されたメール (DKIM) が破損します。
  - [スプーフィング インテリジェンス](anti-spoofing-protection.md) は正しく機能しません。
  - おそらく、誤検知の数が多くなります (不適切とマークされた良いメール)。

  最終的には、検疫への配信を優先して迷惑メール Email フォルダーへの電子メールの配信を防ぐ必要がある場合は、決定です。 ただし、1 つの点は確かです。Defender for Office 365のエクスペリエンスがユーザーの慣れ方と異なる場合は、ユーザーに通知し、基本的なトレーニングを提供する必要があります。 パイロットからの学習を組み込み、ユーザーが電子メール配信の新しい動作に備えるようにします。

- **必要な一括メールと不要な一括メール**: 多くの保護システムでは、ユーザーが自分で一括メールを許可またはブロックできます。 これらの設定は Microsoft 365 に簡単に移行できないため、VIP とそのスタッフと連携して、Microsoft 365 で既存の構成を再作成することを検討する必要があります。

  現在、Microsoft 365 では、メッセージ ソースに基づいて、一部の一括メール (ニュースレターなど) が安全であると見なされています。 現在、これらの "安全な" ソースからのメールは一括としてマークされていないため (一括苦情レベルまたは BCL は 0 または 1)、これらのソースからのメールをグローバルにブロックすることは困難です。 ほとんどのユーザーにとって解決策は、これらの一括メッセージを個別にサブスクライブ解除するか、Outlook を使用して送信者をブロックするように求めることです。 ただし、一部のユーザーは、一括メッセージ自体のブロックやサブスクライブ解除を好まない場合があります。

  一括メールをフィルター処理するメール フロー ルールは、VIP ユーザーが自分でこれを管理したくない場合に役立ちます。 詳細については、「 [メール フロー ルールを使用して一括メールをフィルター処理する」を](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-filter-bulk-mail)参照してください。

## <a name="identify-and-designate-priority-accounts"></a>優先度アカウントを特定して指定する

この機能を利用できる場合、 **優先度アカウント** と **ユーザー タグ** は、重要な Microsoft 365 ユーザーを特定し、レポートで目立つようにするのに役立ちます。 詳細については、「[Microsoft Defender for Office 365のユーザー タグ](user-tags.md)と[優先度アカウントの管理と監視](/microsoft-365/admin/setup/priority-accounts)」を参照してください。

## <a name="next-step"></a>次のステップ

**おめでとうございます**。 Microsoft Defender for Office 365 [への移行](migrate-to-defender-for-office-365.md#the-migration-process)の **準備** フェーズが完了しました。

- [フェーズ 2: セットアップ](migrate-to-defender-for-office-365-setup.md)に進みます。
