---
title: デバイスの要件
description: Microsoft Managed Desktop で動作するデバイスの最小ハードウェア要件とソフトウェア要件の概要
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: b27ad8f4781621a9517507e312feb9be0aa310a3
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034559"
---
# <a name="device-requirements"></a>デバイスの要件

Microsoft Managed Desktop は、サービスに含めるデバイス要件を定期的に評価します。 この記事では、Microsoft Managed Desktop を使用するためにデバイスが満たす必要があるハードウェア要件とソフトウェア要件について説明します。 これらの要件に基づいて、サービスでの使用が既に承認されている特定のデバイスの一覧を確認できます。 ビジネス デバイス サイトの Shop [Windows Proデスクトップの](https://www.microsoft.com/en-us/windows/business/devices)フィルター

> [!NOTE]
> これらの要件は、いつでも変更できますが、ハードウェア要件の変更に関する 30 日間の通知を提供します。 最近変更された要件は、 でマークされます <b>\*</b> 。 

## <a name="check-hardware-requirements"></a>ハードウェア要件の確認

デバイスの仕様を確認する以外に、ダウンロード可能な準備状況評価[](../get-ready/readiness-assessment-downloadable.md)チェッカーを使用して、特定のデバイスが必要な要件を満たしていることを確認することもできます。 また、このツールは、サービスが動作するために必要なネットワーク設定とエンドポイントもチェックします。

## <a name="minimum-requirements"></a>最小要件

Microsoft Managed Desktop に登録するには、デバイスがこれらの要件のすべてを満たすか、または超える必要があります。

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

これらの機能とサービスが使用するテクノロジの詳細については [、「Microsoft Managed Desktop テクノロジ」を参照してください](../intro/technologies.md)。

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
