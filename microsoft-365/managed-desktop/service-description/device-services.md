---
title: Microsoft Managed Desktop デバイス サービス
description: この記事では、Microsoft Managed Desktop のデバイス サービスと制限について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: a1a2871c688d24f87f6194835ef8a655bb2c785c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330273"
---
# <a name="microsoft-managed-desktop-device-services"></a>Microsoft Managed Desktop デバイス サービス

この記事では、Microsoft Managed Desktop デバイスのサービスとサービスの制限について説明します。

## <a name="device-services"></a>デバイス サービス

Microsoft は、Microsoft Managed Desktop デバイスに対して次のサービスを提供します。 推奨される Microsoft Managed Desktop プログラム デバイスの一覧については、[ビジネス デバイスのショップ] ページの [Microsoft Managed Desktop [Windows Proフィルター](https://www.microsoft.com/windows/business/devices)します。

| サービス | 説明 |
| ----- | ----- |
| サポート | サポート エージェントは、デバイスの機能に直接関連する質問に回答し、デバイスの問題を診断します。
| インベントリ | すべてのデバイスは、インベントリと状態の Microsoft Managed Desktop Admin ポータルで追跡されます。
| ファームウェアとドライバーの更新 | 既定では、Microsoft Managed Desktop デバイスは、更新プログラムからファームウェアとドライバーの更新Windowsします。<br><br>すべてのハードウェア パートナーが更新プログラムを更新プログラム経由で展開Windowsではありません。 自動として公開されていない更新プログラムには例外が必要であり、お客様が展開する必要があります。
| アクセサリ | デバイスに付属するアクセサリは、デバイス自体と同じサービスでカバーされますが、保証条件が異なる場合があります。 デバイスを選択する場合は、保証条項を参照してください。
| デバイスのセットアップ | デバイスは、現在のバージョンのデバイスで事前構成されWindows、クラウド経由でアプリと構成を受信します。

デバイスの交換、アップグレード、およびサポート条件については、デバイス プロバイダーとの契約と保証条件を参照してください。

Surface の保証と修理の詳細については、次の情報を参照してください。

- [法人向け Surface ヘルプ センター](https://support.microsoft.com/hub/4339296/surface-for-business-help)
- [デバイスの保証、拡張サービス プラン、および利用規約](https://support.microsoft.com/help/4040687/info-about-warranties-extended-service-plans-and-terms-conditions)

## <a name="device-service-limitations"></a>デバイス サービスの制限

Microsoft は、次のアイテムのサービスを提供しない。

| サービス | 説明 |
| ----- | ----- |  
| カスタマイズ | サービスで提供されるデバイスとアクセサリをカスタマイズできません。<br><br>すべてのデバイスとアクセサリには、標準的なブランド化、仕様、色の組み合わせが用意されています。 アプリケーションの展開とポリシー構成は、IT-as-a-Service によって処理されます。
| データ復旧 | 個人用設定を含むユーザーとチームのデータは、キャッシュ データOneDrive for Businessローカルに存在する場合にのみ保存されます。<br><br>データが意図的にデバイスの内部ストレージ システムに格納されている場合は、Microsoft にデバイスを返す前に、データ復旧を試み、完了する必要があります。
| デバイスのセットアップ | デバイスは顧客の住所に配信されます。 デバイスの電源をオンにし、顧客がセットアップする必要があります。
