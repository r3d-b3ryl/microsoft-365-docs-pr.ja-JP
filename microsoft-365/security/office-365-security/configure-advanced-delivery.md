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
ms.openlocfilehash: a9c1c6f7635b87e25adcb121db79f67d4ec1988f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789000"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>サードパーティのフィッシング シミュレーションをユーザーに配信し、フィルター処理されていないメッセージを SecOps メールボックスに配信する構成

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> この記事で説明する機能はプレビューで、すべてのユーザーが利用できるとは言え、変更される可能性があります。

既定で組織を[](secure-by-default.md)セキュリティで保護するために、Exchange Online Protection (EOP) では、マルウェアまたは高信頼フィッシングとして識別されるメッセージの安全なリストやフィルター バイパスは許可されません。 ただし、フィルター処理されていないメッセージの配信を必要とする特定のシナリオがあります。 以下に例を示します。

- **サード パーティのフィッシング シミュレーション**: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱なユーザーを特定するのに役立ちます。
- **セキュリティ操作 (SecOps)** メールボックス: セキュリティ チームがフィルター処理されていないメッセージ (良いメッセージと悪いメッセージの両方) を収集および分析するために使用する専用のメールボックス。

これらの特定の _シナリオで_ これらのメッセージがフィルター Microsoft 365されるのを防ぐには、Microsoft 365の高度な _配信ポリシーを_ 使用します。 <sup>\*</sup>高度な配信ポリシーにより、これらのシナリオのメッセージで次の結果が得られます。

- EOP と Microsoft Defender のフィルターは、Office 365に対してアクションを実行しません。<sup>\*</sup>
- [スパムとフィッシングのゼロアワー パージ (ZAP)](zero-hour-auto-purge.md) は、これらのメッセージに対して何も実行しません。<sup>\*</sup>
- [これらのシナリオでは](alerts.md) 、既定のシステム通知はトリガーされません。
- [Defender の AIR とクラスター化では、Office 365](office-365-air.md)メッセージは無視されます。
- 特に、サード パーティ製のフィッシング シミュレーションの場合:
  - [管理者の申請は](admin-submission.md) 、メッセージがフィッシング シミュレーション キャンペーンの一部であり、実際の脅威ではないという自動応答を生成します。 アラートと AIR はトリガーされません。
  - [セーフ Defender for Office 365](safe-links.md)リンクは、これらのメッセージで特定された URL をブロックまたは削除しません。
  - [セーフ Defender Office 365](safe-attachments.md)添付ファイルは、これらのメッセージ内の添付ファイルを削除しません。

<sup>\*</sup> マルウェアのフィルター処理やマルウェアに対する ZAP をバイパスできない。

高度な配信ポリシーによって識別されるメッセージはセキュリティ上の脅威ではないので、メッセージはシステムオーバーライドとしてマークされます。 管理者は、次のエクスペリエンスでこれらのシステムオーバーライドをフィルター処理して分析できます。

- [ウイルス対策プラン 2 の Defender での脅威エクスプローラー/Office 365検出](threat-explorer.md)
- 脅威[エクスプローラー/リアルタイム検出](mdo-email-entity-page.md)の Email エンティティ ページ
- 脅威 [保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [エンドポイント向け Microsoft Defender での高度な検索](../defender-endpoint/advanced-hunting-overview.md)
- [キャンペーン ビュー](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> でセキュリティ センターを開きます。 [高度な配信] ページに **直接移動するには** 、を開きます <https://security.microsoft.com/advanceddelivery> 。

- この記事の手順を実行するには、アクセス許可を割り当てる必要があります。
  - 高度な配信ポリシーで構成された設定を作成、変更、または削除するには、セキュリティ センターのセキュリティ管理者役割グループのメンバーであり、Exchange Online の組織の管理役割グループ **のメンバーである必要があります**。   
  - 高度な配信ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「セキュリティ センター[のアクセス許可」および「Microsoft 365の](permissions-microsoft-365-security-center.md)アクセス許可」[を参照Exchange Online。](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > ユーザーを対応する Azure Active Directory ロールに追加すると、セキュリティ センターで必要なアクセス許可と、セキュリティ センター内の他の機能に対するアクセス許可Microsoft 365。 詳細については、[「管理者の役割について」](../../admin/add-users/about-admin-roles.md) を参照してください。

## <a name="use-the-security-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>セキュリティ センターを使用して、高度な配信ポリシーで SecOps メールボックスを構成する

1. セキュリティ センターで、[メールの送信] & **[&** ルール] セクションの [高度 \> **な** 配信 \>  \>  \> **] に移動します**。

2. [高度 **な配信] ページ** で **、[SecOps** メールボックス] タブが選択されていることを確認し、次のいずれかの手順を実行します。
   - [編集 ![ ] アイコン [ ](../../media/m365-cc-sc-edit-icon.png) **編集] をクリックします**。
   - フィッシング シミュレーションが構成されていない場合は、[追加] を **クリックします**。

3. 開く **[SecOps** メールボックスの編集] フライアウトで、次のいずれかの手順を実行して、SecOps メールボックスとして指定する既存の Exchange Online メールボックスを入力します。
   - ボックス内をクリックし、メールボックスの一覧を解決し、メールボックスを選択します。
   - ボックス内をクリックすると、メールボックスの識別子 (名前、表示名、エイリアス、電子メール アドレス、アカウント名など) の入力を開始し、結果からメールボックス (表示名) を選択します。

     必要な回数だけこの手順を繰り返します。 配布グループは許可されません。

     既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

4. 完了したら、**[保存]** をクリックします。

構成した SecOps メールボックス エントリは **、[SecOps** メールボックス] タブに表示されます。変更するには、タブの ![ [編集] ](../../media/m365-cc-sc-edit-icon.png) **アイコン [編集]** をクリックします。

## <a name="use-the-security-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>セキュリティ センターを使用して、高度な配信ポリシーでサード パーティのフィッシング シミュレーションを構成する

1. セキュリティ センターで、[メールの送信] & **[&** ルール] セクションの [高度 \> **な** 配信 \>  \>  \> **] に移動します**。

2. [高度 **な配信] ページ** で、[フィッシング シミュレーション] **タブを選択** し、次のいずれかの手順を実行します。
   - [編集 ![ ] アイコン [ ](../../media/m365-cc-sc-edit-icon.png) **編集] をクリックします**。
   - フィッシング シミュレーションが構成されていない場合は、[追加] を **クリックします**。

3. 開く **[サード パーティ製フィッシング シミュレーションの編集] フライ** アウトで、次の設定を構成します。

   - **送信ドメイン**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押したり、ボックスの下に表示される値を選択して、少なくとも 1 つの電子メール アドレス ドメイン (contoso.com など) を入力します。 必要な回数だけこの手順を繰り返します。 最大 10 のエントリを追加できます。
   - **送信 IP**: この設定を展開し、ボックスをクリックして値を入力し、Enter キーを押するか、ボックスの下に表示される値を選択することで、少なくとも 1 つの有効な IPv4 アドレスを入力する必要があります。 必要な回数だけこの手順を繰り返します。 最大 10 のエントリを追加できます。 有効な値は次のとおりです。
     - 単一 IP: たとえば、192.168.1.1。
     - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
     - CIDR IP: たとえば、192.168.0.1/25。
   - **許可** するシミュレーション URL : この設定を展開し、必要に応じて、フィッシング シミュレーション キャンペーンの一部である特定の URL を入力します。この URL は、ボックス内をクリックして値を入力し、Enter キーを押したり、ボックスの下に表示される値を選択したりしてブロックまたは削除する必要があります。 最大 10 のエントリを追加できます。

   既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

4. 完了したら、次のいずれかの手順を実行します。
   - **初回:**[追加] を **クリックし**、[閉じる] を **クリックします**。
   - **既存の編集 :**[保存] を **クリックし** 、[閉じる] を **クリックします**。

構成したサード パーティのフィッシング シミュレーション エントリが [フィッシング シミュレーション] **タブに表示** されます。変更するには、タブの ![ [編集] ](../../media/m365-cc-sc-edit-icon.png) **アイコン [編集]** をクリックします。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>フィルター バイパスが必要なその他のシナリオ

高度な配信ポリシーが役立つ 2 つのシナリオに加えて、フィルター処理をバイパスする必要がある他のシナリオがあります。

- **サード パーティ製フィルター**: ドメインの MXレコードが Office 365 を指していない場合 (メッセージは最初にどこか別の [](secure-by-default.md)場所にルーティングされます)、既定ではセキュリティで保護 *されません。*

  サード パーティのフィルター処理によって既に評価されているメッセージに対して Microsoft のフィルター処理をバイパスするには、メール フロー ルール (トランスポート ルールとも呼ばれる) を使用します。 詳細については、「メール フロー ルール [を使用してメッセージの SCL を設定する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)。

- **レビュー中** の誤検知 : 管理者の申請を通じて Microsoft によって分析中の特定の [](admin-submission.md)メッセージを一時的に許可して、Microsoft に不適切とマークされている既知の良いメッセージ (誤検知) を報告することができます。 すべての上書きと同様に、これらの許容量 **_は_** 一時的なものとすることを強くお勧めします。
