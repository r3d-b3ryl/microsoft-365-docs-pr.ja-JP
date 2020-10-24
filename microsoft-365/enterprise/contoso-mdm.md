---
title: Contoso 社のモバイル デバイス管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が microsoft 365 で microsoft Intune を使用して、自社のデバイスおよびそれらに対して実行されているアプリを管理する方法について説明します。
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753999"
---
# <a name="mobile-device-management-for-contoso"></a>Contoso 社のモバイル デバイス管理

Microsoft 365 for enterprise には、モバイルデバイスとアプリケーションの管理とセキュリティをサポートする Intune および Azure サービスのセットが含まれています。

Contoso 社には、多くのモバイル対応従業員がいます。Contoso 社の場所にオフィスがあり、一部にはオフィスがありません。Contoso 社は従業員の生産性を有効にする方法を必要としましたが、デバイス、これらのデバイスに格納されている Contoso データ、およびアプリケーションの動作を安全に保つ必要がありました。

## <a name="plan"></a>計画

Contoso 社は、Microsoft 365 for enterprise のモバイルデバイス管理の次の Intune ユースケースを特定しました。

- Exchange Online の電子メールとデータを保護して、モバイルデバイスから安全にアクセスできるようにします。
- Contoso 社の従業員向けのデバイス (BYOD) プログラムを実装します。
- Contoso 社の従業員に対して、組織が所有する電話と制限付きのタブレットを使用します。

Contoso 社は Intune を使用して次のことを行いません。

- 従業員が、管理されていないパブリックキオスクから Microsoft 365 に安全にアクセスできるようにします。
- オンプレミスの Microsoft Exchange サーバーが存在しないため、モバイルデバイスから安全にアクセスできるように、オンプレミスの電子メールとデータを保護します。

## <a name="deploy"></a>展開

Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。

- モバイルデバイス管理 (MDM) 機関として Intune を設定し、Azure で Intune を使用してコンテンツを管理し、デバイスを管理する
- 登録および Intune の設定およびデバイスベースの条件付きアクセスポリシー用のデバイス用に、Azure Active Directory (Azure AD) グループを作成しました。

  詳細については、「 [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)」を参照してください。

- Ipad、iMacs、および iPhones、および企業所有の iPhones を備えた従業員をサポートするための Apple デバイスプラットフォームを有効にしました。
- Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。
- 登録されていないデバイスの場合は、Microsoft 365 サービスへのアクセスの認証を必要とする一連のモバイルアプリケーション管理 (MAM) ポリシーを実装します。
- 以下のための Intune ポリシーが作成されています。
  - 許可されたアプリ。
  - 許可されていないアクセスを防止するためのデバイスの暗号化。
  - 6桁の PIN またはパスワード。
  - 非アクティブなタイムアウト時間。
  - Windows 10 デバイス上で Windows Defender を使用して、ウイルス対策およびマルウェア対策および署名の更新を行います。
  - 最新のセキュリティ更新プログラムが含まれている Windows 10 デバイスでの自動更新。
  - 管理対象デバイスへの証明書のプッシュ。
  - ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。

Contoso 社は、適切な Intune デバイスグループに追加することによって、展開済みの Pc と会社所有のスマートフォンおよびタブレットを登録しました。 また、従業員が個人デバイスを登録するための BYOD プログラムも設定しました。 登録済みデバイスは Intune ポリシーを受信します。これにより、管理対象およびセキュリティで保護されたデバイスとそのアプリケーションが生成されます。 登録されていないデバイスには、許可されたアプリケーションを指定するモバイルアプリケーション管理 (MAM) ポリシーがあります。

ここでは、Contoso モバイルデバイス管理の展開アーキテクチャについて説明します。

![Contoso モバイルデバイス管理の展開インフラストラクチャ](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a>次のステップ

Contoso 社が Microsoft 365 の [情報保護機能](contoso-info-protect.md) を使用して、企業全体で重要なデジタル資産を分類、識別、保護する方法について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 のデバイス管理](device-management-roadmap-microsoft-365.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

