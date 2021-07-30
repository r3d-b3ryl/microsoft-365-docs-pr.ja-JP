---
title: ソフトウェア メソッドとプロパティ
description: 最近使用した上位のアラートを取得します。
keywords: apis, graph api, supported apis, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f14da0e999a0ec38c9be7ef36e47b2c786e12e97
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656633"
---
# <a name="software-resource-type"></a>ソフトウェア リソースの種類

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>メソッド

メソッド |戻り値の型 |説明
:---|:---|:---
[ソフトウェアの一覧表示](get-software.md) | ソフトウェア コレクション | 組織のソフトウェア インベントリを一覧表示します。
[ID でソフトウェアを取得する](get-software-by-id.md) | ソフトウェア | ソフトウェア ID で特定のソフトウェアを取得します。
[ソフトウェア バージョンの配布を一覧表示する](get-software-ver-distribution.md)| 配布コレクション | ソフトウェアのバージョンの配布をソフトウェア ID で一覧表示します。
[ソフトウェアによるマシンの一覧表示](get-machines-by-software.md)| MachineRef コレクション | ソフトウェア ID に関連付けられているデバイスの一覧を取得します。
[ソフトウェアによる脆弱性の一覧表示](get-vuln-by-software.md) | [脆弱性の](vulnerability.md) コレクション | ソフトウェア ID に関連付けられている脆弱性の一覧を取得します。
[不足している KB を取得する](get-missing-kbs-software.md) | KB コレクション | ソフトウェア ID に関連付けられている不足している KB の一覧を取得する

## <a name="properties"></a>プロパティ

プロパティ |   種類   |   説明
:---|:---|:---
id | String | ソフトウェア ID
名前 | String | ソフトウェア名
ベンダー | String | ソフトウェア ベンダー名
弱点 | Long | 検出された脆弱性の数
publicExploit | ブール型 | 一部の脆弱性に対してパブリックエクスプロイトが存在する
activeAlert | ブール型 | アクティブアラートは、このソフトウェアに関連付けられている
exposedMachines | Long | 公開されているデバイスの数
impactScore | Double | このソフトウェアの露出スコアの影響
