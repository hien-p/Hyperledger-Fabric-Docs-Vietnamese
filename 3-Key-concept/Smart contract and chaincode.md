Bên cạnh Ledger,  Smart contract chính là lõi của một mạng blockchain.  Nếu ledger chịu trách nghiệm lưu trữ dữ liệu thì smart contract đóng vai trò là chương trình được tạo ra để quản lý phần lưu trữ dữ liệu ấy. 

Trong Hyperledger Fabric thì có thêm một khái niệm mới là chaincode có thể tập hợp các smart contract với nhau để đóng gói và triển khai trên mạng blockchain. 

Ví dụ như các smart contract tập hợp lại và định nghĩa là Vehicle chaincode 

```
Vehicle chaincode {
	car contract;
	boat contract;
	bike contract; 
}

```

Các chức năng trong smart contract có thể thực hiện là get,put,delete đối với các data trong ledger. khi tạo ra một transaction sẽ thay đổi nội dung trong ledger. 

Ngoài ra các smart contract cũng liên quan đến cấu hình, hệ thống để gom lại thành system chaincode. Các chaincode này sẽ được triển khai trên các Docker Container riêng giúp developer có thể dễ dàng quản lý và update chaincode

Một trong những ví dụ build smart contract bằng nodejs 
```
async createAsset(ctx, id, color, size, owner, Appraiseved ) {
	const Asset = { 
	ID: id,
	Color: color,
	size: size,
	owner: owner,
	Appraiseved: Appraiseved
	}
	return ctx.stub.putState(id, Buffer.From(JSON.stringfy(asset)))
}
```
