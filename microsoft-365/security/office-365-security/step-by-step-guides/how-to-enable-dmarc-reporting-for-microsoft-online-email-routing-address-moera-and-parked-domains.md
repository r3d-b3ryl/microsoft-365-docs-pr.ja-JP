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
ms.openlocfilehash: 9705f0b11167e148dcc79a9913ae78e3e3828217
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106560"
---
# <a name="how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains"></a>Microsoft Online Email ルーティング アドレス (MOERA) とパークされたドメインの DMARC レポートを有効にする方法

ドメイン 電子メール セキュリティ保護のベスト プラクティスは、ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) を使用してスプーフィングから身を守ることです。 ドメインに対して DMARC をまだ有効にしていない場合は、ドメイン [ベースのメッセージ認証、レポート、および準拠 (DMARC) に関する](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)ページで詳しく説明されている最初の手順です。

このガイドは、メインの DMARC 記事で説明されていないドメインに対して DMARC を構成するのに役立ちます。 これらのドメインには、電子メールに使用していないドメインが含まれますが、保護されていない状態が続く場合、攻撃者が利用する可能性があります。

- ドメイン `onmicrosoft.com` (Microsoft Online Email ルーティング アドレス (MOERA) ドメインとも呼ばれます。
- 現在メールに使用していないパーク済みのカスタム ドメイン。

## <a name="what-youll-need"></a>必要なもの

- ドメインをホストしている DNS プロバイダーをMicrosoft 365 管理センターしてアクセスします。
- Microsoft 365 管理センターで適切な変更を行うためにグローバル 管理として十分なアクセス許可。
- この記事の手順を完了するには、10 分かかります。

## <a name="activate-dmarc-for-moera-domain"></a>MOERA ドメインの DMARC をアクティブ化する

1. <https://admin.microsoft.com> で Microsoft 365 管理センターを開きます。
1. 左側のナビゲーションで、[ **すべて表示**] を選択します。
1. **[設定] を** 展開し、[**ドメイン]** を押します。
1. テナント ドメイン (contoso.onmicrosoft.com など) を選択します。
1. 読み込むページで、 **DNS レコード** を選択します。
1. [ **+ レコードの追加]** を選択します。
1. ポップアップが右側に表示されます。 選択した種類が **TXT (テキスト)** であることを確認します。
1. **TXT 名** として追加`_dmarc`します。
1. 特定の DMARC 値を追加します。
1. **[保存]** を押します。

## <a name="active-dmarc-for-parked-domains"></a>パークされたドメインのアクティブ DMARC

1. SPF がパークされたドメインに対して既に構成されているかどうかを確認します。 手順については、「[スプーフィングを防ぐ SPF の設定 - Office 365 |」を参照してください。Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing#how-to-handle-subdomains)
1. DNS ドメイン プロバイダーに問い合わせてください。
1. 次の DMARC txt レコードを適切な電子メール アドレスで追加するように依頼します `v=DMARC1; p=reject; rua=mailto:d@rua.contoso.com;ruf=mailto:d@ruf.contoso.com`。

## <a name="next-steps"></a>次の手順

DNS の変更が反映されるまで待ち、構成されたドメインのスプーフィングを試みます。 DMARC レコードに基づいて試行がブロックされているかどうかを確認し、DMARC レポートを受け取ります。

## <a name="more-information"></a>詳細情報

[スプーフィング防止に役立つ SPF を設定する - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing)

[DMARC を使用して電子メールを検証する、セットアップ手順 - Office 365 |Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)
