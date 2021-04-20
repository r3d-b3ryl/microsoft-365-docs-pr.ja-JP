---
title: サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Exchange Online Protection (EOP) の高度な配信ポリシーを使用して、サポートされている特定のシナリオ (サード パーティのフィッシング シミュレーションとセキュリティ操作 (SecOps) メールボックスに配信されるメッセージ) でフィルター処理すべきではないメッセージを識別する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 9d737472be5da2af0a0a36beb4b7914b8bfe3a10
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876067"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> この記事で説明する機能はプレビューで、すべてのユーザーが利用できるとは言え、変更される可能性があります。

既定で組織を[](secure-by-default.md)セキュリティで保護するために、Exchange Online Protection (EOP) では、マルウェアや高信頼のフィッシングの評決が発生するメッセージの安全なリストやフィルター バイパスは許可されません。 ただし、フィルター処理されていないメッセージの配信を必要とする特定のシナリオがあります。 次に例を示します。

- **サード パーティのフィッシング シミュレーション**: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。
- **セキュリティ操作 (SecOps)** メールボックス: セキュリティ チームがフィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を収集および分析するために使用する専用のメールボックス。

Microsoft 365 の高度な配信ポリシーを使用して、これらの特定のシナリオでこれらのメッセージがフィルター処理されるのを防 <sup>\*</sup> ぐ。 高度な配信ポリシーにより、次のシナリオのメッセージはフィルター処理されません。

- EOP と Microsoft Defender 365 のフィルター Office、これらのメッセージに対してアクションを実行しません。<sup>\*</sup>
- [スパムとフィッシングのゼロアワー パージ (ZAP)](zero-hour-auto-purge.md) は、これらのメッセージに対してアクションを実行しません。<sup>\*</sup>
- [これらのシナリオでは](alerts.md) 、既定のシステム通知はトリガーされません。
- [365 の Defender の AIR とクラスター Office、これらの](office-365-air.md) メッセージは無視されます。
- 特に、サード パーティ製のフィッシング シミュレーションの場合:
  - [管理者の申請は](admin-submission.md) 、メッセージがフィッシング シミュレーション キャンペーンの一部であり、実際の脅威ではないという自動応答を生成します。 アラートと AIR はトリガーされません。
  - [Defender for Office 365](safe-links.md) のセーフ リンクは、これらのメッセージで特定された URL をブロックまたは削除しません。
  - [Defender for Office 365](safe-attachments.md) の安全な添付ファイルは、これらのメッセージ内の添付ファイルを削除しません。

<sup>\*</sup> マルウェアのフィルター処理やマルウェアに対する ZAP をバイパスできない。

高度な配信ポリシーによって識別されるメッセージはセキュリティ上の脅威ではないので、メッセージはシステムオーバーライドとしてマークされます。 管理者は、次のエクスペリエンスでこれらのシステムオーバーライドをフィルター処理して分析できます。

- [脅威エクスプローラー/365 プラン 2 の Defender Officeリアルタイム検出](threat-explorer.md)
- 脅威[エクスプローラー/リアルタイム検出](mdo-email-entity-page.md)の Email エンティティ ページ
- 脅威 [保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [エンドポイント向け Microsoft Defender での高度な検索](../defender-endpoint/advanced-hunting-overview.md)
- [キャンペーン ビュー](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [高度な配信] ページに **直接移動するには** 、を開きます <https://protection.office.com/advanceddelivery> 。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - 高度な配信ポリシーで構成された設定を作成、変更、または削除するには、セキュリティ **&** コンプライアンスセンターのセキュリティ管理者役割グループのメンバーであり **、Exchange Online** の組織の管理役割グループのメンバーである必要があります。  
  - 高度な配信ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「セキュリティ コンプライアンス [センターのアクセス許可」と「exchange Online &アクセス](permissions-in-the-security-and-compliance-center.md) 許可 [」を参照してください](/exchange/permissions-exo/permissions-exo)。

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>セキュリティ サービス コンプライアンス &を使用して、高度な配信ポリシーでサード パーティのフィッシング シミュレーションを構成する

1. セキュリティ 管理コンプライアンス センター&、 **脅威管理ポリシー** \> **の [高度な配信** \> **] に移動します**。

2. [高度 **な配信] ページ** で、[フィッシング シミュレーション] **タブを** 選択し、[編集] を **クリックします**。

3. 開く **サード パーティのフィッシング シミュレーション の** フライアウトで、次の設定を構成します。

   - **送信ドメイン**: 少なくとも 1 つの電子メール アドレス ドメインが必要です (たとえば、contoso.com)。 最大 10 のエントリを追加できます。
   - **送信 IP**: 少なくとも 1 つの有効な IPv4 アドレスが必要です。 最大 10 のエントリを追加できます。 有効な値は次のとおりです。
     - 単一 IP: たとえば、192.168.1.1。
     - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
     - CIDR IP: たとえば、192.168.0.1/25。
   - **許可するシミュレーション URL**: 必要に応じて、ブロックまたは削除すべきではないフィッシング シミュレーション キャンペーンの一部である特定の URL を入力します。 最大 10 のエントリを追加できます。

4. 完了したら、[保存] を **クリックします。**

構成したサード パーティのフィッシング シミュレーション エントリが [フィッシング シミュレーション] **タブに表示** されます。変更するには、タブの **[編集]** をクリックします。

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>高度な配信ポリシー& SecOps メールボックスを構成するには、セキュリティ コンプライアンス センターを使用します。

1. セキュリティ 管理コンプライアンス センター&、脅威管理ポリシーの **[高度な** \> **配信** \> **] に移動します**。

2. [高度 **な配信] ページ** で **、[SecOps** メールボックス] タブを選択し、[編集] を **クリックします**。

3. 開く **SecOps メールボックス** のフライアウトで、SecOps メールボックスとして指定する既存の Exchange Online メールボックスの電子メール アドレスを入力します。 配布グループは許可されません。

4. 完了したら、**[保存]** をクリックします。

構成した SecOps メールボックス エントリは **、[SecOps** メールボックス] タブに表示されます。変更するには、タブの **[編集]** をクリックします。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>フィルター バイパスが必要なその他のシナリオ

高度な配信ポリシーが役立つ 2 つのシナリオに加えて、フィルター処理をバイパスする必要がある他のシナリオがあります。

- **サード パーティ製のフィルター**: ドメインのMX レコードが Office 365 を指していない場合 (メッセージは最初にどこか [](secure-by-default.md)別の場所にルーティングされます)、既定ではセキュリティ保護は *利用できません*。

  サード パーティのフィルター処理によって既に評価されているメッセージに対して Microsoft のフィルター処理をバイパスするには、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用します。「メッセージで [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)を設定するには、メール フロー ルールを使用する」を参照してください。

- **レビュー中** の誤検知 : 管理者の申請を通じて Microsoft によって分析中の特定の [](admin-submission.md)メッセージを一時的に許可して、Microsoft に不適切とマークされている既知の良いメッセージ (誤検知) を報告することができます。 すべての上書きと同様に、これらの手当を **_一_** 時的に行うのを強くお勧めします。