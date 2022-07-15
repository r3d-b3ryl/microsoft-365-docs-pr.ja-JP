---
title: Microsoft Online Email ルーティング アドレス (MOERA) とパークされたドメインの DMARC レポートを有効にする方法
description: MOERA とパークされたドメインの DMARC を構成する手順。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: dbe994ee0cba90f37acf7dcbd92c3b0d81d673a3
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66798214"
---
# <a name="how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains"></a>Microsoft Online Email ルーティング アドレス (MOERA) とパークされたドメインの DMARC レポートを有効にする方法

ドメイン 電子メール セキュリティ保護のベスト プラクティスは、ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) を使用してスプーフィングから身を守ることです。 ドメインに対して DMARC をまだ有効にしていない場合は、ドメイン [ベースのメッセージ認証、レポート、および準拠 (DMARC) に関する](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)ページで詳しく説明されている最初の手順です。

このガイドは、上記のガイドで説明されていないドメイン (Microsoft Online Email ルーティング アドレス (MOERA) とも呼ばれる contosocorp.onmicrosoft.com ドメインとパークされたドメインの両方に対して DMARC を構成できるように設計されています。これは、まだ電子メールに使用していない可能性がありますが、保護されるまで攻撃者が利用する可能性があります。

## <a name="what-youll-need"></a>必要なもの

- Microsoft 365 管理センターと、ドメインをホストしている DNS プロバイダーへのアクセス
- Microsoft 365 管理 センターで適切な変更を行うためにグローバル 管理として十分なアクセス許可
- 次の手順を完了するには 10 分

## <a name="activate-dmarc-for-moera-domain"></a>MOERA ドメインの DMARC をアクティブ化する

1. [Microsoft 365 管理 センター](https://admin.microsoft.com)にログインします。
1. 左側のナビゲーションで、[ **すべて表示**] を選択します。
1. [設定] を展開し、[ **ドメイン]** を押します。
1. テナント ドメイン (contoso.onmicrosoft.com) を選択します。
1. 読み込むページで、 **DNS レコード** を選択します。
1. [ **+ レコードの追加]** を選択します。
1. ポップアップが右側に表示され、選択した種類が **TXT (テキスト)** であることを確認します。
1. TXT 名として_dmarcを追加します。
1. 特定の DMARC 値を追加します。
1. **[保存]** を押します。

## <a name="active-dmarc-for-parked-domains"></a>パークされたドメインのアクティブ DMARC

1. 「[SPF を設定してスプーフィングを防止する - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing#how-to-handle-subdomains)
1. DNS ドメイン プロバイダーに問い合わせてください。
1. 適切な電子メール アドレスを使用して、この DMARC txt レコードを追加するように依頼します `v=DMARC1; p=reject; rua=mailto:d@rua.contoso.com;ruf=mailto:d@ruf.contoso.com`。

## <a name="next-steps"></a>次の手順

DNS の変更が反映されるまで待ち、構成されたドメインのスプーフィングを試みます。 DMARC レコードに基づいて試行がブロックされているかどうかを確認し、DMARC レポートを受け取ります。

## <a name="more-information"></a>詳細情報

[スプーフィング防止に役立つ SPF を設定する - Office 365 |](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing)
 Microsoft Docs [DMARC を使用して電子メールの検証、セットアップ手順 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)
