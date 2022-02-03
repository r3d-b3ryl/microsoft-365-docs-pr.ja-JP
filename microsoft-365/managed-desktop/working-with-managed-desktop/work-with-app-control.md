---
title: アプリ制御を操作する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: b87da099ace71b13b03bb9d9247bc4cbfe420dc4
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322390"
---
# <a name="work-with-app-control"></a>アプリ制御を操作する

アプリコントロールが環境に展開された後、ユーザーと Microsoft Managed Desktop Operations の両方に継続的な責任があります。 たとえば、環境に新しいアプリを追加したり、信頼できる署名者を追加 (または削除) したりします。 セキュリティを強化するには、ユーザーにリリースする前に、すべてのアプリにコード署名が必要です。 アプリの発行元の詳細には、署名者に関する情報が含まれます。

## <a name="add-a-new-app"></a>新しいアプリの追加

**新しいアプリを追加するには、**

1. アプリをアプリに[追加Microsoft Intune](/mem/intune/apps/apps-win32-app-management)。
1. テスト リング内の任意のデバイスにアプリを展開します。
1. 標準のビジネス プロセスに従ってアプリをテストします。
1. [アプリケーションとサービス ログ **\Microsoft\Windows\AppLocker] でイベント ビューアーを確認します**。 **8003 イベントまたは** **8006 イベントを探** します。 これらのイベントは、アプリがブロックされる可能性を示します。 すべてのアプリ ロッカー イベントとその意味の詳細については、「 [Using Event Viewer with AppLocker」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。
1. これらのイベントが見つけた場合は、Microsoft Managed Desktop Operations を使用して署名者要求を開きます。

## <a name="add-or-remove-a-trusted-signer"></a>信頼できる署名者を追加 (または削除) する

署名者要求を開く場合は、最初に重要な発行元の詳細を提供する必要があります。

**信頼できる署名者を追加 (または削除) するには、次の方法を実行します。**

1. [発行元の詳細を収集します](#gather-publisher-details)。
1. Microsoft Managed Desktop Operations でチケットを開き、署名者ルールを要求し、次の詳細を含める。  
    - アプリケーション名
    - アプリケーションのバージョン
    - 説明
    - 変更の種類 ("add" または "remove")  
    - Publisher詳細 (例: "O=<publisher name>,L=<location>,S=State,C=Country")

> [!NOTE]
> アプリの信頼を削除するには、同じ手順に従いますが、[変更の種類] を **削除に** 設定 *します*。

このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  Day 0       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  2 日目       |
|広範な質問     | Enforced        |  3 日目       |

ロールアウト中は、いつでも展開を一時停止またはロールバックできます。 一時停止またはロールバックするには、Microsoft Managed Desktop Operations を使用して別のサポート要求を開きます。

> [!NOTE]
> 署名者ルールのリリースを一時停止する場合は、別のロールアウトを開始する前に、そのルールをロールバックまたは完了する必要があります。

## <a name="gather-publisher-details"></a>発行元の詳細を収集する

**アプリの発行元データにアクセスするには、次の方法を実行します。**

1. 監査モード ポリシーが適用されているテスト リングで Microsoft Managed Desktop デバイスを探します。
1. デバイスにアプリをインストールします。
1. そのデバイスでイベント ビューアーを開きます。
1. イベント ビューアーで、[アプリケーションとサービス ログ **\Microsoft\** Windows] に移動し、[**AppLocker] を選択します**。
1. **8003** または **8006** イベントを検索し、イベントから情報をコピーします。
    - アプリケーション名
    - アプリケーションのバージョン
    - 説明
    - Publisher詳細 (たとえば、「O=、L=<publisher name><location>、S=State、C=Country」)
