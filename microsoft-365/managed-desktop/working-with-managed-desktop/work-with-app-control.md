---
title: アプリ制御を操作する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289461"
---
# <a name="work-with-app-control"></a>アプリ制御を操作する

ご使用の環境でアプリ管理が展開されると、お客様と Microsoft が管理するデスクトップ操作の両方に、継続的な責任があります。 たとえば、環境に新しいアプリを追加したり、信頼できる署名者を追加 (または削除) したりする場合があります。 セキュリティを強化するには、ユーザーにリリースする前に、すべてのアプリをコード署名する必要があります。 アプリの発行元の詳細には、署名者に関する情報が含まれています。


## <a name="add-a-new-app"></a>新しいアプリの追加

新しいアプリを追加するには、次の手順を実行します。

1. アプリを [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)に追加します。
2. アプリをテストリングの任意のデバイスに展開します。 
3. 標準のビジネスプロセスに従ってアプリをテストします。 
4. **Application And Services Logs\Microsoft\Windows\AppLocker**の下にあるイベントビューアーを調べて、 **8003**または**8006**イベントを探します。 これらのイベントは、アプリがブロックされることを示します。 すべてのアプリケーションのロッカーイベントとその意味については、「 [AppLocker でイベントビューアーを使用する](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)」を参照してください。
5. これらのイベントのいずれかが見つかった場合は、Microsoft マネージドデスクトップ操作を使用して署名者の要求を開きます。

## <a name="add-or-remove-a-trusted-signer"></a>信頼できる署名者を追加 (または削除) する

署名者の要求を開くときには、最初にいくつかの重要な発行者の詳細を提供する必要があります。 その後、次の手順を実行します。

1. [発行元の詳細を収集](#gather-publisher-details)します。
2. Microsoft マネージドデスクトップ操作でチケットを開き、署名者ルールを要求し、次の詳細情報を含めます。  
    - アプリケーション名 
    - アプリケーションのバージョン 
    - 説明 
    - 変更の種類 ("追加" または "削除")  
    - 発行元の詳細 (例: "O = <publisher name> , L = <location> , S = State, C = Country") 

> [!NOTE]
> アプリの信頼を削除するには、同じ手順を実行しますが、[ **変更の種類** ] を [ *削除*] に設定します。

このスケジュールに従って、ポリシーは展開グループに段階的に展開されます。


|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  0日       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  2 日目       |
|広範な質問     | Enforced        |  3 日目       |


ロールアウトの間に、いつでも展開を一時停止またはロールバックすることができます。 これを行うには、操作を使用して別のサービス要求を開きます。

> [!NOTE]
> 署名者ルールのリリースを一時停止した場合は、別のロールアウトを開始する前に、そのルールをロールバックするか、完了する必要があります。

## <a name="gather-publisher-details"></a>発行元の詳細を収集する

アプリの発行元データにアクセスするには、次の手順を実行します。

1. テストリングで監査モードポリシーが適用された Microsoft マネージドデスクトップデバイスを検索します。 
2. デバイスにアプリをインストールしようとしています。
3. そのデバイスでイベントビューアーを開きます。 
4. イベントビューアーで、[ **アプリケーションとサービス Logs\Microsoft\Windows**] に移動し、[ **AppLocker**] を選択します。 
5. 任意の **8003** または **8006** イベントを検索し、そのイベントから情報をコピーします。 
    - アプリケーション名 
    - アプリケーションのバージョン 
    - 説明 
    - 発行元の詳細 (例: "O = <publisher name> , L = <location> , S = State, C = Country") 
