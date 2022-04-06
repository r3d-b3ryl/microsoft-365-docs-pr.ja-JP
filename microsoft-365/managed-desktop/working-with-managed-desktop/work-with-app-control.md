---
title: アプリ制御を操作する
description: アプリコントロールを管理する方法について学習します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 99979a08a67245d471b33ce26e4b7f35790fead5
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64569911"
---
# <a name="work-with-app-control"></a>アプリ制御を操作する

アプリコントロールが環境に展開された後は、ユーザーとユーザーの両方Microsoft Managed Desktop継続的な責任を負います。 たとえば、環境に新しいアプリを追加したり、信頼できる署名者を追加 (または削除) したりします。 セキュリティを強化するには、ユーザーにリリースする前に、すべてのアプリにコード署名が必要です。 アプリの発行元の詳細には、署名者に関する情報が含まれます。

## <a name="add-a-new-app"></a>新しいアプリの追加

**新しいアプリを追加するには、**

1. アプリをアプリに追加[Microsoft Intune](/mem/intune/apps/apps-win32-app-management)。
1. テスト リング内の任意のデバイスにアプリを展開します。
1. 標準のビジネス プロセスに従ってアプリをテストします。
1. [アプリケーションとイベント ビューアー **ログ\Microsoft\Windows\AppLocker] のWindowsを確認します**。 **8003 イベントまたは** **8006 イベントを探** します。 これらのイベントは、アプリがブロックされる可能性を示します。 すべてのアプリ ロッカー イベントとその意味の詳細については、「[Using イベント ビューアー AppLocker」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。
1. これらのイベントが見つけた場合は、署名者要求を開き、[操作] Microsoft Managed Desktopします。

## <a name="add-or-remove-a-trusted-signer"></a>信頼できる署名者を追加 (または削除) する

署名者要求を開く場合は、最初に重要な発行元の詳細を提供する必要があります。

**信頼できる署名者を追加 (または削除) するには、次の方法を実行します。**

1. [発行元の詳細を収集します](#gather-publisher-details)。
1. 署名者ルールを要求Microsoft Managed Desktop、次の詳細を含むチケットを開きます。  
    - アプリケーション名
    - アプリケーションのバージョン
    - 説明
    - 変更の種類 ("add" または "remove")  
    - Publisher詳細 (例: `O=<publisher name>,L=<location>,S=State,C=Country`)

> [!NOTE]
> アプリの信頼を削除するには、同じ手順に従いますが、[変更の種類] を **削除に** 設定 *します*。

このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

|展開グループ|ポリシーの種類|Timing|
|---|---|---|
|テスト|監査|Day 0|
|第 1|Enforced|1 日目|
|高速|Enforced|2 日目|
|広範な質問|Enforced|3 日目|

ロールアウト中は、いつでも展開を一時停止またはロールバックできます。 一時停止またはロールバックするには、別のサポート要求を [操作] Microsoft Managed Desktopします。

> [!NOTE]
> 署名者ルールのリリースを一時停止する場合は、別のロールアウトを開始する前に、そのルールをロールバックまたは完了する必要があります。

## <a name="gather-publisher-details"></a>発行元の詳細を収集する

**アプリの発行元データにアクセスするには、次の方法を実行します。**

1. 監査モード Microsoft Managed Desktop適用されているテスト リング内のデバイスを検索します。
1. デバイスにアプリをインストールします。
1. そのデバイスのイベント ビューアーを開きます。
1. [アプリケーション] イベント ビューアー[アプリケーションとサービス ログ **\Microsoft\** Windows] に移動し、[**AppLocker] を選択します**。
1. **8003** または **8006** イベントを検索し、イベントから情報をコピーします。
    - アプリケーション名
    - アプリケーションのバージョン
    - 説明
    - Publisher詳細 (例: `O=<publisher name>, L=<location>, S=State, C=Country`)
