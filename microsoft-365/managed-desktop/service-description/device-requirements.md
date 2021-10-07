---
title: デバイスの要件
description: デバイスがデバイスで動作する最小ハードウェア要件とソフトウェア要件の概要Microsoft マネージド デスクトップ
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1ce5f0c3782b8e8082d0e1ede53339a190b7259f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209467"
---
# <a name="device-requirements"></a>デバイスの要件

Microsoft マネージド デスクトップに含めるデバイス要件を定期的に評価します。 この記事では、デバイスがデバイスで動作するために満たす必要があるハードウェア要件とソフトウェア要件Microsoft マネージド デスクトップ。 これらの要件に基づいて、サービスでの使用が既に承認されている特定のデバイスの一覧を確認できます。 ビジネス デバイス Microsoft マネージド デスクトップ[ショップ サイトのWindows Proフィルター](https://www.microsoft.com/en-us/windows/business/devices)

> [!NOTE]
> これらの要件は、いつでも変更できますが、ハードウェア要件の変更に関する 30 日間の通知を提供します。 最近変更された要件は、 でマークされます <b>\*</b> 。 

## <a name="check-hardware-requirements"></a>ハードウェア要件の確認

デバイスの仕様を確認する以外に、ダウンロード可能な準備状況評価[](../get-ready/readiness-assessment-downloadable.md)チェッカーを使用して、特定のデバイスが必要な要件を満たしていることを確認することもできます。 また、このツールは、サービスが動作するために必要なネットワーク設定とエンドポイントもチェックします。

## <a name="minimum-requirements"></a>最小要件

デバイスは、これらの要件Microsoft マネージド デスクトップ以上の要件を満たす必要があります。

### <a name="manufacturer"></a>製造元

デバイスは、次のいずれかの製造元によって作成されている必要があります。

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>インストール済みソフトウェア

デバイスには、次のソフトウェアがプレインストールされている必要があります。

- <b>\*</b>Windows 10またはWindows 11: Enterprise、Pro、Pro ワークステーション エディション
- 64 ビット バージョンの Microsoft 365 Apps for enterprise 
- 適用可能なすべてのデバイス ドライバー


### <a name="physical-features"></a>物理機能

デバイスには、次の機能が必要です。

- UEFI セキュア ブートに対して有効 
- 信頼できるプラットフォーム モジュール 2.0 
- 仮想化ベースのセキュリティが可能 
- [BIOS でサポートされるハイパーバイザー](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) で保護されたコード整合性

これらの機能とサービスが使用するテクノロジの詳細については[、「Microsoft マネージド デスクトップ」を参照してください](../intro/technologies.md)。

> [!NOTE]
>- ARMプロセッサはサポートされていません。
>- <b>\*</b>Windows 11 には追加の[ハードウェア要件があります](/windows/whats-new/windows-11-requirements)。

デバイスは、ストレージとメモリの次の制限を満たすか、または超える必要があります。

- ブート ドライブは、ハード ディスク以外の種類である必要があります。 たとえば、SSD、NVMe、および eMMC ドライブはすべて有効な選択肢です。
- ブート ドライブの容量は 128 GB 以上である必要があります。
- 内部デバイス メモリ (RAM) は 8 GB 以上である必要があります。

デバイスが 2020 年 7 月 1 日以降に作成された場合は、IR カメラ、指紋リーダー、または両方を使用して、デバイスをサポート[Windows Hello。](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-features"></a>推奨される機能

次の機能を備えたデバイスを選択すると、ユーザーのエクスペリエンスが向上します。

- Intel vPro-platform プロセッサまたは AMD Ryzen Proプロセッサ
- 容量が 256 GB 以上の SSD タイプのブート ドライブ
- 16 GB 以上の内部デバイス メモリ (RAM)
- モダン スタンバイのサポート
- デバイスがセキュリティで保護されたコア PC の種類
- カーネル DMA 保護をサポート
