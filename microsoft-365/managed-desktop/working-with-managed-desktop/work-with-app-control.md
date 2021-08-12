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
ms.openlocfilehash: 0a0072cbc5738ae78c151650d8186eb34f952602015b7068909a2d276664684a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53807158"
---
# <a name="work-with-app-control"></a>アプリ制御を操作する

アプリコントロールが環境に展開された後は、ユーザーとユーザーの両方Microsoft マネージド デスクトップ継続的な責任があります。 たとえば、環境に新しいアプリを追加したり、信頼できる署名者を追加 (または削除) することができます。 セキュリティを強化するには、ユーザーにリリースする前に、すべてのアプリにコード署名が必要です。 アプリの発行元の詳細には、署名者に関する情報が含まれます。


## <a name="add-a-new-app"></a>新しいアプリの追加

新しいアプリを追加するには、次の手順を実行します。

1. アプリを[アプリに追加](/mem/intune/apps/apps-win32-app-management)Microsoft Intune。
2. テスト リング内の任意のデバイスにアプリを展開します。 
3. 標準のビジネス プロセスに従ってアプリをテストします。 
4. [アプリケーションとサービス ログ **\Microsoft\Windows\AppLocker]** でイベント ビューアーを確認し **、8003** イベントまたは **8006** イベントを探します。 これらのイベントは、アプリがブロックされる可能性を示します。 すべてのアプリ ロッカー イベントとその意味の詳細については、「Using Event Viewer with [AppLocker」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。
5. これらのイベントが見つけた場合は、署名者要求を開き、[操作] Microsoft マネージド デスクトップします。

## <a name="add-or-remove-a-trusted-signer"></a>信頼できる署名者を追加 (または削除) する

署名者要求を開く場合は、最初に重要な発行元の詳細を提供する必要があります。 次に、次の手順に従います。

1. [発行元の詳細を収集します](#gather-publisher-details)。
2. 署名者ルールを要求Microsoft マネージド デスクトップ、次の詳細を含むチケットを開きます。  
    - アプリケーション名 
    - アプリケーションのバージョン 
    - 説明 
    - 変更の種類 ("add" または "remove")  
    - Publisher詳細 (例: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> アプリの信頼を削除するには、同じ手順に従いますが、[変更の種類] を **[削除]** に *設定します*。

このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。


|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  Day 0       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  2 日目       |
|広範な質問     | Enforced        |  3 日目       |


ロールアウト中は、いつでも展開を一時停止またはロールバックできます。 これを行うには、Operations を使用して別のサービス要求を開きます。

> [!NOTE]
> 署名者ルールのリリースを一時停止する場合は、別のロールアウトを開始する前に、そのルールをロールバックまたは完了する必要があります。

## <a name="gather-publisher-details"></a>発行元の詳細を収集する

アプリの発行元データにアクセスするには、次の手順を実行します。

1. 監査モード Microsoft マネージド デスクトップ適用されているテスト リング内のデバイスを検索します。 
2. デバイスにアプリをインストールします。
3. そのデバイスでイベント ビューアーを開きます。 
4. イベント ビューアーで、[アプリケーションとサービス ログ **\Microsoft\Windows] に** 移動し **、[AppLocker] を選択します**。 
5. **8003** または **8006** イベントを検索し、イベントから情報をコピーします。 
    - アプリケーション名 
    - アプリケーションのバージョン 
    - 説明 
    - Publisher詳細 (例: "O= <publisher name> , L= <location> , S=State, C=Country")