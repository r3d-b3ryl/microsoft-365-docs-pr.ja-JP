---
title: Microsoft Defender for Endpointアラートを管理する
description: '[アラートの管理] メニューを使用して、アラートの状態を変更し、抑制ルールを作成してアラートを非表示にし、コメントを送信し、個々のアラートの変更履歴を確認します。'
keywords: アラートの管理、管理、アラート、状態、新規、進行中、解決済み、アラートの解決、抑制、抑制、抑制、ルール、コンテキスト、履歴、コメント、変更
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c14447301cfa6abf83c231361c020d261eeb87a9
ms.sourcegitcommit: 349f0f54b0397cdd7d8fbb9ef07f1b6654a32d6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2022
ms.locfileid: "65623432"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Microsoft Defender for Endpointアラートを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender for Endpoint は、アラートを通じて、悪意のあるイベント、属性、コンテキスト情報の可能性を通知します。 新しいアラートの概要が **セキュリティ操作ダッシュボード** に表示され、 **アラート キュー** 内のすべてのアラートにアクセスできます。

アラートを管理するには、アラート **キュー** でアラートを選択するか、個々のデバイスの [デバイス] ページの [ **アラート** ] タブを選択します。

いずれかの場所でアラートを選択すると、[ **アラート管理] ウィンドウが表示されます**。

:::image type="content" source="images/atp-alerts-selected.png" alt-text="[アラート管理] ウィンドウと [アラート] キュー" lightbox="images/atp-alerts-selected.png":::

このビデオでは、新しいMicrosoft Defender for Endpointアラート ページを使用する方法について説明します。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4yiO5]

## <a name="link-to-another-incident"></a>別のインシデントへのリンク

アラートから新しいインシデントを作成したり、既存のインシデントにリンクしたりできます。

## <a name="assign-alerts"></a>アラートの割り当て

アラートがまだ割り当てられていない場合は、[自分 **に割り当てる** ] を選択してアラートを自分に割り当てることができます。

## <a name="suppress-alerts"></a>アラートを抑制する

アラートがMicrosoft 365 Defenderに表示されないようにする必要があるシナリオがある場合があります。 Defender for Endpoint を使用すると、組織内の既知のツールやプロセスなど、無害であることが知られている特定のアラートに対する抑制ルールを作成できます。

抑制ルールは、既存のアラートから作成できます。 必要に応じて、無効にしたり、再び有効にしたりできます。

抑制ルールが作成されると、ルールが作成された時点から有効になります。 ルールは、ルールの作成前に、キューに既に存在する既存のアラートには影響しません。 ルールは、ルールの作成後に設定された条件を満たすアラートにのみ適用されます。

抑制ルールには、次の 2 つのコンテキストから選択できます。

- **このデバイスでアラートを抑制する**
- **組織内のアラートを抑制する**

ルールのコンテキストを使用すると、ポータルに表示される内容を調整し、実際のセキュリティ アラートのみがポータルに表示されるようにすることができます。

次の表の例を使用して、抑制ルールのコンテキストを選択できます。

|Context|定義|シナリオ例|
|---|---|---|
|**このデバイスでアラートを抑制する**|同じアラート タイトルとその特定のデバイス上のアラートのみが抑制されます。 <p> そのデバイス上の他のすべてのアラートは抑制されません。|<ul><li>セキュリティ研究者が、組織内の他のデバイスを攻撃するために使用された悪意のあるスクリプトを調査しています。</li><li>開発者は、チームの PowerShell スクリプトを定期的に作成します。</li></ul>|
|**組織内のアラートを抑制する**|どのデバイスでも同じアラート タイトルを持つアラートは抑制されます。|<ul><li>無害な管理ツールは、組織内のすべてのユーザーによって使用されます。</li></ul>|

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>アラートを抑制し、新しい抑制ルールを作成する

アラートを抑制または解決するタイミングを制御するカスタム ルールを作成します。 アラートのタイトル、侵害のインジケーター、および条件を指定することで、アラートが抑制されるタイミングのコンテキストを制御できます。 コンテキストを指定すると、アラートのアクションとスコープを構成できるようになります。

1. 抑制するアラートを選択します。 これにより、[ **アラート管理** ] ウィンドウが表示されます。

2. [ **抑制ルールの作成] を選択します**。

    これらの属性を使用して抑制条件を作成できます。 AND 演算子は各条件の間に適用されるため、すべての条件が満たされた場合にのみ抑制が行われます。

    - ファイル SHA1
    - ファイル名 - ワイルドカードがサポートされています
    - フォルダー パス - ワイルドカードがサポートされています
    - IP アドレス
    - URL - ワイルドカードがサポートされています
    - コマンド ライン - ワイルドカードがサポートされています

3. **トリガー IOC** を選択します。

4. アラートのアクションとスコープを指定します。

   アラートは自動的に解決するか、ポータルから非表示にすることができます。 自動的に解決されるアラートは、アラート キュー、アラート ページ、およびデバイスのタイムラインの解決済みセクションに表示され、Defender for Endpoint API 全体で解決済みとして表示されます。

   非表示としてマークされたアラートは、デバイスの関連付けられたアラートとダッシュボードの両方でシステム全体から抑制され、Defender for Endpoint API 間ではストリーミングされません。

5. ルール名とコメントを入力します。

6. [**保存**] をクリックします。

#### <a name="view-the-list-of-suppression-rules"></a>抑制ルールの一覧を表示する

1. ナビゲーション ウィンドウで、**アラート抑制設定**\>選択します。

2. 抑制ルールの一覧には、組織内のユーザーが作成したすべてのルールが表示されます。

抑制ルールの管理の詳細については、「抑制ルールの[管理](manage-suppression-rules.md)」を参照してください。

## <a name="change-the-status-of-an-alert"></a>アラートの状態を変更する

調査の進行に合わせてアラートの状態を変更することで、アラートを ( **新規**、 **進行中**、解決 **済** みとして) 分類できます。 これにより、チームがアラートに対応する方法を整理して管理できます。

たとえば、チーム リーダーはすべての **新しい** アラートを確認し、詳細な分析のために **進行中** キューに割り当てることを決定できます。

または、チーム リーダーは、アラートが問題でない(セキュリティ管理者に属しているデバイスなど)、または以前のアラートを介して処理されているデバイスから送信されたアラートが問題でないことがわかっている場合は、 **解決済** みキューにアラートを割り当てる場合があります。

## <a name="alert-classification"></a>アラートの分類

分類を設定しないか、アラートが真のアラートか偽アラートかを指定できます。 真陽性/偽陽性の分類を提供することが重要です。 この分類は、アラートの品質を監視し、アラートをより正確にするために使用されます。 "決定" フィールドは、"真の陽性" 分類に対する追加の忠実性を定義します。

## <a name="add-comments-and-view-the-history-of-an-alert"></a>コメントを追加し、アラートの履歴を表示する

コメントを追加し、アラートに関する履歴イベントを表示して、アラートに加えられた以前の変更を確認できます。

変更またはコメントがアラートに加えられるたびに、[ **コメントと履歴** ] セクションに記録されます。

追加されたコメントは直ちにウィンドウに表示されます。

## <a name="related-topics"></a>関連項目

- [抑制ルールの管理](manage-suppression-rules.md)
- [Microsoft Defender for Endpoint アラート キューを表示して整理する](alerts-queue.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Microsoft Defender for Endpointアラートに関連付けられているファイルを調査する](investigate-files.md)
- [Microsoft Defender for Endpoint デバイスの一覧のデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpointでユーザー アカウントを調査する](investigate-user.md)
