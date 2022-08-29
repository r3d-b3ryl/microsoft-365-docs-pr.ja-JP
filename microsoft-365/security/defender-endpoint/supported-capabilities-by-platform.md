---
title: プラットフォーム別にサポートされるMicrosoft Defender for Endpoint機能
description: Windows 10 デバイス、サーバー、および Windows 以外のデバイスでサポートされているMicrosoft Defender for Endpoint機能について説明します。
keywords: オンボード, Microsoft Defender for Endpointオンボード, sccm, グループ ポリシー, mdm, ローカル スクリプト, 検出テスト
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8370bfcae9efbac72642292d41b844cc7b20219a
ms.sourcegitcommit: ab32c6e19af08837aaa84a058653c3a209d366ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2022
ms.locfileid: "67445208"
---
# <a name="supported-microsoft-defender-for-endpoint-capabilities-by-platform"></a>プラットフォーム別にサポートされるMicrosoft Defender for Endpoint機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[デバイスをオンボードし、Microsoft Defender for Endpoint機能を構成する](onboard-configure.md)方法について説明します。

次の表に、プラットフォーム別にサポートされているMicrosoft Defender for Endpoint機能に関する情報を示します。

|オペレーティング システム  |Windows 10 & 11  |Windows Server 2012 R2 <sup>[[1](#fn1)]</sup>, <br> 2016 <sup>[[1](#fn1)]</sup>, <br> 2019 & 2022、 <br> 1803+ |macOS |Linux| 
|---------|---------|---------|---------|---------|
|**防止**    |         |         |         |         | 
|攻撃面の縮小ルール     | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)     |  ![不要](images/svg/check-no.svg)       |  ![不要](images/svg/check-no.svg)        |
|コントロールされたフォルダー アクセス     | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)    |  ![不要](images/svg/check-no.svg)       |  ![不要](images/svg/check-no.svg)        |
|デバイス制御     | ![はい。](images/svg/check-yes.svg)        | ![いいえ](images/svg/check-no.svg)   |  ![はい。](images/svg/check-yes.svg)       |  ![不要](images/svg/check-no.svg)        |  
|ファイアウォール      | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)    |  ![不要](images/svg/check-no.svg)       |  ![不要](images/svg/check-no.svg)        |
|ネットワーク保護      | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)   |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
|次世代の保護       | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![はい。](images/svg/check-yes.svg)       |  ![はい。](images/svg/check-yes.svg)         |
|改ざん防止        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![はい。](images/svg/check-yes.svg)       |  ![不要](images/svg/check-no.svg)         |
|Web Protection       | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)     |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
||||||
|**検出**     |         |         |         |       |
|高度な追求        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg) |  ![はい。](images/svg/check-yes.svg)       |  ![はい。](images/svg/check-yes.svg)         |
|カスタム ファイル インジケーター         | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![はい。](images/svg/check-yes.svg)       |  ![はい。](images/svg/check-yes.svg)         |
|カスタム ネットワーク インジケーター        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
|EDR ブロック       | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![不要](images/svg/check-no.svg)       |  ![不要](images/svg/check-no.svg)        |
|パッシブ モード          | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![はい。](images/svg/check-yes.svg)       |  ![はい。](images/svg/check-yes.svg)         |
|センス検出センサー          | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)   |  ![はい。](images/svg/check-yes.svg)       |  ![はい。](images/svg/check-yes.svg)         |
|エンドポイント&ネットワーク デバイス検出      | ![はい。](images/svg/check-yes.svg)        | ![不要](images/svg/check-no.svg)  |  ![不要](images/svg/check-no.svg)       |  ![不要](images/svg/check-no.svg)        |
|脆弱性管理          | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg) |  ![はい。](images/svg/check-yes.svg)       |  ![はい。](images/svg/check-yes.svg)         |
||||||
|**Response**     |         |         |         ||
|自動調査&応答 (AIR)        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)  |  ![不要](images/svg/check-no.svg)       |  ![不要](images/svg/check-no.svg)        |
|デバイス応答機能: 調査パッケージの収集、AV スキャンの実行        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)   |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)][[3](#fn3)]</sup>       |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)][[3](#fn3)]</sup>        |
|デバイスの分離        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)   |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)][[3](#fn3)]</sup>       |  ![不要](images/svg/check-no.svg)    |
|ファイル応答機能: ファイルの収集、詳細な分析、ファイルのブロック、停止、検疫のプロセス        | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg)   |  ![いいえ](images/svg/check-no.svg) <sup>[[4](#fn4)]</sup>      |  ![いいえ](images/svg/check-no.svg) <sup>[[4](#fn4)]</sup>    |
|ライブ応答       | ![はい。](images/svg/check-yes.svg)        | ![はい。](images/svg/check-yes.svg) |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![はい。](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |


(<a id="fn1">1</a>) Windows Server 2012 R2 と 2016 の最新の統合ソリューションを参照します。 詳細については、「 [Defender for Endpoint サービスへの Windows サーバーのオンボード」を](configure-server-endpoints.md)参照してください。

(<a id="fn2">2</a>) 機能は現在プレビュー段階です ([プレビュー機能Microsoft Defender for Endpoint](preview.md)) 

(<a id="fn3">3</a>) Live Response を使用した応答機能 [2] 

(<a id="fn4">4</a>) Live Response を使用してファイルのみを収集する [2]  
>[!NOTE]
>Windows 7、8.1、Windows Server 2008 R2 には、System Center Endpoint Protection (SCEP) を使用した EDR センサーと AV のサポートが含まれています。

