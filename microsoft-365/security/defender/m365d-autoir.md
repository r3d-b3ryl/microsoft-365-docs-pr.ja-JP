---
title: Microsoft 365 Defender での自動調査と応答
description: 自動調査と応答機能 (セルフヒーリングとも呼ばれる) の概要をMicrosoft 365 Defender
keywords: 自動, 調査, アラート, トリガー, アクション, 修復, 自己修復
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 07/19/2022
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: a72e5df2f6e46956d857160da72734b94a3b6a30
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481110"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender での自動調査と応答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

組織が[Microsoft 365 Defender](microsoft-365-defender.md)を使用している場合、セキュリティ運用チームは、悪意のあるアクティビティや疑わしいアクティビティまたはアーティファクトが検出されるたびに、Microsoft 365 Defender ポータル内でアラートを受け取ります。 脅威の一見終わりのないフローを考えると、セキュリティ チームは多くの場合、大量のアラートに対処するという課題に直面します。 幸いにも、Microsoft 365 Defenderには、セキュリティ運用チームがより効率的かつ効果的に脅威に対処するのに役立つ自動調査と対応 (AIR) 機能が含まれています。

この記事では、AIR の概要を説明し、次の手順と追加のリソースへのリンクを含みます。

## <a name="how-automated-investigation-and-self-healing-works"></a>自動調査と自己修復のしくみ

セキュリティ アラートがトリガーされると、セキュリティ運用チームがそれらのアラートを調べて、組織を保護するための手順を実行します。 警告の優先順位付けと調査には、多くの時間がかかる場合があります。調査実行中に新しい警告が出されるような状況では、この傾向が特に強くなります。 セキュリティ運用チームは、監視および保護を必要とする脅威の膨大さに圧倒されてしまう可能性があります。 自動調査と応答機能は、自己修復機能を備えたMicrosoft 365 Defenderで役立ちます。

次のビデオを見て、自己修復のしくみを確認します。 <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Microsoft 365 Defenderでは、自動調査と自動修復機能を使用した対応は、デバイス、電子メール & コンテンツ、ID で動作します。
 
> [!TIP]
> この記事では、自動調査と応答のしくみについて説明します。 これらの機能を構成するには、「[Microsoft 365 Defenderでの自動調査と応答機能の構成](m365d-configure-auto-investigation-response.md)」を参照してください。

## <a name="your-own-virtual-analyst"></a>独自の仮想アナリスト

階層 1 または階層 2 のセキュリティ運用チームに仮想アナリストがいるとします。 仮想アナリストは、セキュリティ運用チームであれば実行するであろう脅威の調査と修復の最適な手順を模倣して実行します。 仮想アナリストは、無制限の容量で 24 時間 365 日稼働し、調査と脅威の修復の大きな負荷を引き受ける可能性があります。 このような仮想アナリストは、対応にかかる時間を大幅に短縮し、セキュリティ運用チームを他の重要な脅威や戦略的プロジェクトに解放することができます。 このシナリオが SF のように聞こえる場合は、そうではありません。 このような仮想アナリストは、Microsoft 365 Defender スイートの一部であり、その名前は *自動調査と応答* です。

自動調査と対応機能により、セキュリティ運用チームは、セキュリティ アラートやインシデントに対処する組織の能力を大幅に向上できます。 自動調査と対応により、調査と対応アクティビティに対処するコストを削減し、脅威保護スイートを最大限に活用できます。 自動調査と対応機能は、次の方法でセキュリティ運用チームを支援します。

1. 脅威に対してアクションを実行する必要があるかどうかの判断。
2. 必要な修復アクションの実行 (または推奨)。
3. 他の調査を行うべきかどうか、どのような調査を行うべきかの決定。
4. 必要に応じた、他の警告に対するプロセスの反復。

## <a name="the-automated-investigation-process"></a>自動調査のプロセス

アラートによってインシデントが作成され、自動調査を開始できます。 自動調査では、証拠の各部分に対する判定が行われます。 判定には次のものがあります。
- *悪意*
- *疑わしい* 
- *脅威は検出されませんでした* 

悪意のあるエンティティまたは疑わしいエンティティに対する修復アクションが識別されます。 修復アクションの例を次に示します。

- ファイルを検疫に送信する
- プロセスの停止
- デバイスの分離
- URL をブロックする 
- その他の操作

詳細については、「[Microsoft 365 Defenderの修復アクション](m365d-remediation-actions.md)」を参照してください。

組織に対して [自動調査機能と応答機能を構成する方法](m365d-configure-auto-investigation-response.md) に応じて、修復アクションが自動的に実行されるか、セキュリティ運用チームの承認に基づいてのみ実行されます。 保留中でも完了でも、すべてのアクションが [アクション センター](m365d-action-center.md)に一覧表示されます。

調査の実行中にその他の関連する警告が発生した場合は、それらの警告は調査が完了するまで調査に追加され続けます。 影響を受けるエンティティが他の場所で見られる場合、自動調査はそのエンティティを含むようにその範囲を拡大し、調査プロセスが繰り返されます。 

Microsoft 365 Defenderでは、各自動調査によって、Microsoft Defender for Identity、Microsoft Defender for Endpoint、および次の表に示すように、Microsoft Defender for Office 365。 

|エンティティ |脅威対策サービス  |
|:---------|:---------|
|デバイス (エンドポイントまたはマシンとも呼ばれます) |[Defender for Endpoint](../defender-endpoint/automated-investigations.md) |      
|オンプレミスの Active Directory ユーザー、エンティティの動作、アクティビティ     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|Emailコンテンツ (ファイルと URL を含めることができる電子メール メッセージ)     |[Defender for Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> すべてのアラートによって自動調査がトリガーされるわけではありません。また、すべての調査によって自動修復アクションが実行されるわけではありません。 組織に対して自動調査と対応を構成する方法によって異なります。 [自動調査機能と応答機能の構成に関するページを](m365d-configure-auto-investigation-response.md)参照してください。

## <a name="viewing-a-list-of-investigations"></a>調査の一覧を表示する

調査を表示するには、[ **インシデント]** ページに移動します。 インシデントを選択し、[調査] タブ **を** 選択します。詳細については、「 [自動調査の詳細と結果](m365d-autoir-results.md)」を参照してください。

## <a name="automated-investigation--response-card"></a>応答カード&自動調査 

新しい自動調査&応答カードは、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で利用できます。 使用可能な修復アクションの合計数に対するこの新しいカードの可視性。 カードには、すべてのアラートの概要と、各アラートに必要な承認時間も表示されます。

:::image type="content" source="../../media/automated-investigation-response-card.png" alt-text="自動調査&応答カードを示すスクリーンショット。":::

セキュリティ運用チームは、自動調査&応答カードを使用して、アクション センターで承認リンクを選択し、適切なアクションを実行することで、 **アクション センター** にすばやく移動できます。 このカードを使用すると、セキュリティ運用チームは承認待ちのアクションをより効果的に管理できます。 


## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn のこのラーニング モジュールを使用して、Microsoft 365 Defenderがインシデントの調査と対応に自動自己修復を使用する方法を理解します。

|トレーニング: |Microsoft 365 Defender を使用する自動自己修復|
|---|---|
|![Microsoft 365 Defenderトレーニング アイコンを使用して自己修復を自動化します。](../../media/m365d-autoir/m365-defender-auto-self-healing.svg)| Microsoft 365 Defenderでは、AI を使用してインシデントの修復を自動化し、セキュリティ運用チームがより効率的かつ効果的に脅威に対処できるようにします。 <p> 11 分 - 5 単位 |

> [!div class="nextstepaction"]
> [スタート>](/learn/modules/defender-self-healing/)

## <a name="next-steps"></a>次の手順

- [自動調査と応答の前提条件を確認する](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [組織の自動調査と対応を構成する](m365d-configure-auto-investigation-response.md)
- [アクション センターの詳細](m365d-action-center.md)
