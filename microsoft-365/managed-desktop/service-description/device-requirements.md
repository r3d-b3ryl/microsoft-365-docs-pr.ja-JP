---
title: デバイスの要件
description: デバイスが Microsoft マネージド デスクトップで動作するために必要なハードウェアおよびソフトウェアの最小要件の概要
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88b1ba657b4823d90a41b28b01362760676410ba
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032693"
---
# <a name="device-requirements"></a>デバイスの要件

Microsoft マネージド デスクトップは、サービスに含めるデバイス要件を定期的に評価します。 この記事では、Microsoft マネージド デスクトップで動作するためにデバイスが満たす必要があるハードウェアおよびソフトウェアの要件について説明します。 これらの要件に基づいて、サービス[](device-list.md)での使用が既に承認されている特定のデバイスの一覧を確認できます。

> [!NOTE]
> これらの要件は、いつでも変更できますが、このような変更に関する通知は 90 日間提供されます。 最近変更された要件には、次のマークが付いている **\*** 必要があります。 

## <a name="check-hardware-requirements"></a>ハードウェア要件の確認

デバイスの仕様の確認に加え、ダウンロード可能な準備状況の[](../get-ready/readiness-assessment-downloadable.md)評価チェックを使用して、特定のデバイスが必要な要件を満たしていることを確認することもできます。 また、このツールは、サービスが動作するために必要なネットワーク設定とエンドポイントもチェックします。

## <a name="minimum-requirements"></a>最小要件

Microsoft マネージド デスクトップに登録するには、デバイスがこれらの要件のすべて以上を満たしている必要があります。

### <a name="manufacturer"></a>製造元

デバイスは、次のいずれかの製造元によって作成されている必要があります。

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>インストールされているソフトウェア

デバイスには、次のソフトウェアがプレインストールされている必要があります。

- Windows 10 Enterprise、Pro、または Pro Workstation エディション
- {64 ビットバージョンの Office実行 {I will double-check name w/ Office colleagues]}
- 該当するデバイス ドライバーすべて


### <a name="physical-features"></a>物理的な機能

デバイスには、次の機能が必要です。

- UEFI セキュア ブートが有効 
- トラステッド プラットフォーム モジュール 2.0 
- 仮想化ベースのセキュリティが可能 
- ハイパーバイザーで保護されたコード整合性をサポートする 

これらの機能と、サービスが使用するテクノロジの詳細については、「Microsoft マネージド デスクトップ テクノロジ」 [を参照してください](../intro/technologies.md)。

> [!NOTE]
> ARMプロセッサはサポートされていません。

デバイスは、ストレージとメモリに関する次の制限を満たすか、または超える必要があります。

- ブート ドライブは、ハード ディスク以外の種類である必要があります。 たとえば、SSD、NVMe、eMMC ドライブはすべて有効な選択肢です。
- ブート ドライブには、128 GB 以上の容量が必要です。

デバイスが 2020 年 7 月 1 日より後に作成された場合は [、Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)をサポートするために IR カメラ、指紋リーダー、または両方が必要です。

## <a name="recommended-requirements"></a>推奨される要件

これらは絶対要件ではありませんが、次の機能を備えたデバイスを選択すると、ユーザーのエクスペリエンスが向上します。

- Intel vPro-platform プロセッサまたは AMD Ryzen Pro プロセッサ
- 256 GB 以上の容量の SSD タイプのブート ドライブ
- モダン スタンバイのサポート
- デバイスの種類がセキュリティで保護されたコア PC である
- カーネル DMA 保護のサポート